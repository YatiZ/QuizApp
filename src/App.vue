<script setup>
import {RouterView} from "vue-router"
import QuizesView from "./views/QuizesView.vue";
// import QuizView from "./views/QuizView.vue";
</script>
<template>
  <div class="container">
    <RouterView/>
    
    
  </div>
</template>
<style scoped>
.container{
  max-width: 100%;
  display: flex;
  margin-left: 15px;
  justify-content: center;

}
/* @media only screen and(min-width:768px) {
   .container{
    max-width: 768px;
    margin: 0 auto;
   }
}
@media only screen and(min-width: 1024px){
  .container{
    max-width: 1024px;
    margin: 0 auto;
  }
} */


@media only screen and(min-width: 280px){
  .container{
    max-width: 280px;
    margin: 0 auto;
  }
  
}
</style>
