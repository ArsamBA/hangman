<template>
   <div class="landing-section-component-wrapper">
     <div class="landing-section-description-wrapper">
       <h1 class="landing-section-title">{{ title }}</h1>
       <p class="landing-section-description">{{ description }}</p>
       <div class="landing-section-button-wrapper">
         <input type="button" :value="buttonText" buttonLink="/" />
       </div>
     </div>
     <div class="landing-section-svg-container">
       <!-- //* this is where the svg get imported -->
       <slot />
     </div>
   </div>
 </template>
 
 <script lang="ts" setup>
 const props = defineProps<{
   title: string;
   description: string;
   buttonText: string;
 }>();
 
 </script>
 
 <style lang="scss" scoped>
 @import "@/assets/scss/global.scss";
 .landing-section-component-wrapper {
   display: flex;
   flex-direction: column;
   align-items: center;
   justify-content: space-between;
   margin-bottom: 80px;
 }
 .landing-section-description-wrapper {
   display: flex;
   flex-direction: column;
   align-items: center;
   justify-content: center;
   .landing-section-title {
     font-size: 36px;
     text-align: center;
     line-height: 54px;
   }
   .landing-section-description {
     text-align: center;
     font-size: 18px;
     line-height: 27px;
     margin-top: 25px;
   }
   .landing-section-second-description {
     width: 100%;
     text-align: center;
     font-size: 18px;
     line-height: 27px;
     @include mq(lg) {
       text-align: left;
     }
     @include mq(xl) {
       padding: 0px 11px;
       line-height: 45px;
       font-size: 24px;
     }
   }
  .landing-section-button-wrapper {
    margin-top: 20px;
    width: 100%;
    input{
      border: 1px solid $primary;
      outline: none;
      border-radius: 8px;
      font-size: 20px;
      color: $primary;
      padding: 10px 15px;

      &:hover {
        background: $primary;
        color: #fff;
      }
    }
   }
  }
 .landing-section-svg-container {
   width: 90%;
   display: flex;
   align-items: center;
   justify-content: center;
   margin-top: 50px;
   @include mq(lg) {
     margin: unset;
   }
   img {
     width: 100%;
     max-width: 560px;
   }
 }
 @include mq(sm) {
   .landing-section-svg-container {
     width: 80%;
   }
 }
 @include mq(md) {
   .landing-section-svg-container {
     width: 70%;
   }
 }
 @include mq(lg) {
   .landing-section-component-wrapper {
     flex-direction: row;
   }
   .landing-section-description-wrapper {
     flex-basis: calc(100% / 2 - 20px);
     .landing-section-title {
       text-align: left;
       line-height: 60px;
       width: 100%;
 
       // &:lang(fa) {
       //   text-align: right;
       // }
     }
     .landing-section-description {
       text-align: left;
       margin-top: 50px;
       width: 100%;
       line-height: 32px;
 
       // &:lang(fa) {
       //   text-align: right;
       // }
     }
     .landing-section-button-wrapper {
       align-self: flex-start;
       margin-top: 50px;
     }
   }
   .landing-section-svg-container {
     flex-basis: calc(100% / 2 - 20px);
   }
 }
 @include mq(xl) {
   .landing-section-description-wrapper {
     .landing-section-title {
       line-height: 96px;
       font-size: 64px;
       padding: 0px 11px;
     }
     .landing-section-description {
       line-height: 45px;
       font-size: 24px;
       padding: 0px 11px;
     }
   }
 }
 </style>
 