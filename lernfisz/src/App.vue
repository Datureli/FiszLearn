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
.fade-enter-active, .fade-leave-active {
 transform: rotate(30deg);
 transition: all 3s ease;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
transform: rotate(0);
 transition: all 3s ease;
}
</style>
