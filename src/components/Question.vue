<script setup>
  import {defineProps, defineEmits} from "vue"

  const emit = defineEmits(["selectOption"])
  const {question} = defineProps(['question'])

  const emitSelectedOption = (isCorrect) =>{
    emit("selectOption",isCorrect)
  }

</script>

<template>
    <div class="question-container">
            <h1 class="question">
                {{ question.text }}
            </h1>
        </div>
        <div class="options-container">
           <div v-for="option in question.options" :key="option.id" class="option" @click="emitSelectedOption(option.isCorrect)">
            <p class="option-label">{{ option.label }}</p>
            <div class="option-value"><p>{{ option.text }}</p></div>
           </div>
        </div>
        
</template>

<style scoped>
.question-container{
    margin-top: 20px;
    

  }
  .options-container{
    padding-right: 20px;
  }
  .question{
    margin-bottom: 20px;
    font-size: 20px;
    color: aliceblue;
  }
  .option{
    display: flex;
    margin-bottom: 20px;
    cursor: pointer;
  }
  .option-label{
    background-color: bisque;
    width: 50px;
    /* height: fit-content; */
    font-size: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 5px;
  }
  .option-value{
    background-color: rgb(244,239,239);
    width: 100%;
    display: flex;
    align-items: center;
    font-size: 20px;
    padding: 0 20px;
  }
  @media only screen and(max-width: 900px){
     .question{
      font-size: 20px;
     }
  }
</style>