<script setup>
 import q from "../data/quizes.json"
 import {ref, watch} from "vue"
 import Card from "../components/Card.vue"
 

 const quizes = ref(q)
 const search = ref("")

 watch(search, ()=>{
  quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value))
 })
</script>

<template>
   <div>
    
    <header>
      <h1 style="color:aliceblue">Quizes</h1>
      <input type="text" placeholder="Search..." v-model.trim="search">
    </header>
    <div class="options-container">
      <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
       <!-- <div class="card" v-for="quiz in quizes" :key="quiz.id">
        <img :src="quiz.img" alt="math" >
        <div class="card-text">
          <h2>{{ quiz.name }}</h2>
          <p>{{ quiz.questions.length}} questions</p>
        </div>
       </div> -->
    </div>
   </div>

</template>

<style scoped>

header{
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  align-items: center;
}
header h1{
  font-weight: bold;
  margin-right: 30px;

}
header input{
  border: none;
  background-color:rgba(15, 237, 15, 0.471) ;
  padding: 10px;
  border-radius: 5px;
  color: aliceblue;
}

.options-container{
  display: flex;
  flex-wrap: wrap;
  margin-top: 40px;

}
/* Card styles */
.card{
  width: 310px;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.902);
  margin-bottom: 35px;
  margin-right: 20px;
  cursor: pointer;
}
.card img{
  width: 100%;
  height: 190px;
  margin: 0;

}
.card .card-text{
  padding: 0 5px;

}
.card .card-text h2{
  font-weight: bold;
}
</style>
