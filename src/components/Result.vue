<script setup>
 import {defineProps} from "vue"
 import {RouterLink} from "vue-router"

 const {quizQuestionLength,numberOfCorrectAnswers} = defineProps(["quizQuestionLength","numberOfCorrectAnswers"])
</script>

<template>
    <div class="results">
        <p>Your Results....</p>
        <h1>
            {{ numberOfCorrectAnswers }}/{{ quizQuestionLength }}
        </h1>
        <RouterLink to="/" class="back">Go Back</RouterLink>
    </div>
</template>
<style scoped>
.results{
    text-align: center;
    padding: 100px 0;
    color: aliceblue;
}
p{
    font-size: 25px;
    color: aliceblue;

}
h1{
    font-size: 80px;
    color: aliceblue;
}
.back{
    font-size: 35px;
}
</style>