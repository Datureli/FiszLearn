<template>
  <div>
      <transition name="flip">
      <h1>sdadas</h1>
      </transition>
      <ul>
   
      <li v-for="(question,index) in questions" :key="index" class="card">
          <transition name="flip">
        <p :key="question.flipped" >{{ question.flipped ? question.answer : question.question }}</p>
          </transition>
        <button @click="toggleQuestion(question)" >show answer</button>
      </li>
       
      </ul>
  </div>
</template>

<script>
export default {
data() {
    return {
        show: true,
        questions: [
            {
                question: 'Co to jest git?',
                answer: 'Git jest to rozproszony system kontroli wersji',
                  flipped: false,
            },
              {
                question: 'Co to jest github??',
                answer: 'Github to serwis internetowy,hostujący repozytoria git w chmurze',
                flipped: false,
            },
              {
                question: 'Co to jest git?',
                answer: 'Git jest to rozproszony system kontroli wersji',
                flipped: false,
            },
              {
                question: 'Co to jest git?',
                answer: 'Git jest to rozproszony system kontroli wersji',
                flipped: false,
            }
        ]
    }
},
 methods: {
    toggleQuestion(question){
      question.flipped = !question.flipped;
    }
}
}
</script>

<style>
.card  {
    width: 280px;
    height: 400px;
    border: 1px solid black;
    margin:30px  auto;
    text-decoration: none;
    background-color: green;
}
.cardRotate {
    transform: rotate(180deg);
    animation: 3s rotate ease;
}
button {
    width: 100px;
    height: 30px;
    background-color: blue;
    color: wheat;
    border-radius: 5px;
    outline: none;
    margin-top: 200px;
}

.flip-enter-active {
    transition: all 0.4s ease;
  }
  
  .flip-leave-active {
    display: none;
  }
  
  .flip-enter, .flip-leave {
    transform: rotateY(180deg);
    opacity: 0;
  
  }
</style>