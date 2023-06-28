<template>
<div class="e-card" style="height: 350px; width: 400px;">
    <table>
      <tr>
        <td>
          <div class="profilepic">
            <template v-if="isDataLoaded">
               <img :src="require('@/assets/profpic.jpg')" style="height: 75px; border-radius:40px;"/>   
            </template>
            <template v-else>
              <ejs-skeleton  width="60px" shape="Circle" cssClass="e-customize"
                             shimmerEffect="Pulse"></ejs-skeleton>
            </template>
            
            
          </div>
         
        </td>
        <td>
          <div class="profilename">
            <template v-if="isDataLoaded">
               <label id="name">Laura Chauhan</label><br> 
            </template>
            <template v-else>
            <ejs-skeleton shape="Text" height="15px" width="200px" cssClass="e-customize"
                          shimmerEffect="Pulse" ></ejs-skeleton>
          </template>
          </div>
        </td>
      </tr>
    </table>
    <div class="post">
      <template v-if="isDataLoaded">
       <img :src="require('@/assets/nature.jpg')" style="height: 250px; width: 380px; padding: 10px;"> 
    </template>
    <template v-else>
      <ejs-skeleton shape="Rectangle" height="250px" width="375px" cssClass="e-customize"
                    shimmerEffect="Pulse" ></ejs-skeleton>
    </template>
    </div>
  </div>
  
</template>

<script>
import { SkeletonComponent } from '@syncfusion/ej2-vue-notifications';
export default {
  name: "App",
  components:{
    'ejs-skeleton' : SkeletonComponent
  },

  data: function () {
    return {
      isDataLoaded : false
  }
  },
  mounted(){
    this.loadData();
  },
  methods:{
    async loadData()
    {
      await new Promise((resolve) =>setTimeout(resolve,20000));
      this.isDataLoaded = true;
    }
  }  
}

</script>

 <style>
 .e-customize .e-skeleton.e-shimmer-wave::after{
  background-image: linear-gradient(90deg, transparent calc(50% - 100px),
    rgb(30 128 234 / 50%) 50%,
    transparent calc(50% + 100px));
 }
 .e-customize.e-skeleton.e-skeleton-circle{
        background-color: #a8c1f2;
 }
 .e-customize.e-skeleton.e-skeleton-text{
        background-color: #a8c1f2;
 }
 .e-customize.e-skeleton.e-skeleton-rectangle{
        background-color: #a8c1f2;
 }
 .profilepic
 {
  height: 70px;
    width: 30px;
    margin-top: 18px;
    margin-left: 0px;
    padding-left: 10px;
 }
 .profilename
 {
    margin-top: 10px;
    margin-left: 17px;
    
    font-size: larger;
 }
 .post
 {
    margin-left:3px;
    padding: 10px;
    margin-top: -5px;
 }
 #name
 {
  font-size:larger;
 }
 @import '../node_modules/@syncfusion/ej2-base/styles/material.css';
 @import '../node_modules/@syncfusion/ej2-vue-layouts/styles/material.css';
 @import "../node_modules/@syncfusion/ej2-vue-notifications/styles/material.css";
 </style>
 