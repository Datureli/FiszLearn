<template>
<div>
  <question-card />
</div>
</template>

<script>
import QuestionCard from './components/QuestionCard.vue'

export default {
  name: 'App',
  components: {
    QuestionCard
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
