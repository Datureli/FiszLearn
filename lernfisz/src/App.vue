<template>
  <div>
    <header>
      <Navigation />
    </header>
    <transition name="slide" mode="out-in">
      <question-card />
    </transition>

    <random-card />
  </div>
</template>

<script>
import QuestionCard from "./components/QuestionCard.vue";
import RandomCard from "./components/RandomCard.vue";
import Navigation from "./components/Navigation.vue";

export default {
  name: "App",
  components: {
    Navigation,
    RandomCard,
    QuestionCard,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
header {
  width: 100%;
  height: 60px;
  background-color: black;
  color: wheat;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.slide-enter-active,
.slide-leave-active {
  transition: opacity 1.5s, transform 2.5s;
}
.slide-enter,
.slide-leave-to {
  opacity: 0;
  transform: translateX(-30%);
}
</style>
