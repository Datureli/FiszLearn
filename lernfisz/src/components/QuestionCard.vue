<template>
  <div>
    <div class="displayCards">
      <ul>
        <li
          ref="card"
          v-for="(question, index) in questions.slice(0, 6)"
          :key="index"
          class="card"
        >
          {{ question.filterQuestions }}
          <transition name="flip" mode="out-in">
            <p :key="question.change" class="card__">
              {{ question.change ? question.answer : question.question }}
            </p>
          </transition>
          <button @click="toggleQuestion(question)">
            {{ question.change ? "Back" : "Show answer" }}
          </button>
        </li>
      </ul>
    </div>
    <button @click="randomizeQuestionCard()">randomize</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      questions: [
        {
          question: "Co to jest git?",
          answer: "Git jest to rozproszony system kontroli wersji",
          change: false,
        },
        {
          question: "Co to jest github??",
          answer:
            "Github to serwis internetowy,hostujący repozytoria git w chmurze",
          change: false,
        },
        {
          question: "Czym się różni '==' od '==='?",
          answer:
            "'==' porównuje wartości zmiennych,'===' sprawdza też czy zmienne mają ten sam typ.",
          change: false,
        },
        {
          question: "Czym jest :before i :after?",
          answer:
            ":before oraz :after umożliwiają dodanie kontentu przed i za elementem.",
          change: false,
        },
        {
          question: "Czym jest :before i :after?",
          answer:
            ":before oraz :after umożliwiają dodanie kontentu przed i za elementem.",
          change: false,
        },
        {
          question: "Czym jest :before i :after?",
          answer:
            ":before oraz :after umożliwiają dodanie kontentu przed i za elementem.",
          change: false,
        },
        {
          question: "Czym jest :before i :after?",
          answer:
            ":before oraz :after umożliwiają dodanie kontentu przed i za elementem.",
          change: false,
        },
        {
          question: "Czym jest :before i :after?",
          answer:
            ":before oraz :after umożliwiają dodanie kontentu przed i za elementem.",
          change: false,
        },
        {
          question: "Czym jest :before i :after?",
          answer:
            ":before oraz :after umożliwiają dodanie kontentu przed i za elementem.",
          change: false,
        },
        {
          question: "Czym jest :before i :after?",
          answer:
            ":before oraz :after umożliwiają dodanie kontentu przed i za elementem.",
          change: false,
        },
      ],
    };
  },
  methods: {
    toggleQuestion(question) {
      question.change = !question.change;
    },
    randomize(question) {
      for (let i = question.length - 1; i > 0; i--) {
        let randomIndex = Math.floor(Math.random() * i);
        let temp = question[i];
        this.$set(question, i, question[randomIndex]);
        this.$set(question, randomIndex, temp);
      }
    },
    randomizeQuestionCard() {
      this.questions.reverse();
      console.log(this.questions);
    },
  },
};
</script>

<style scoped>
.card {
  display: block;
  width: 150px;
  height: 175px;
  padding: 80px 50px;
  border-radius: 7px;
  text-align: center;
  justify-content: center;
  line-height: 27px;
  cursor: pointer;
  position: relative;
  color: #fff;
  font-weight: 600;
  font-size: 20px;
  -webkit-box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  -moz-box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  margin: 30px auto;
  text-decoration: none;
  background-color: green;
}
.cardRotate {
  transform: rotate(180deg);
  animation: 3s rotate ease;
}
button {
  border-radius: 5px;
  border: 1px solid #87cb84;
  background-color: #87cb84;
  padding: 8px 15px;
  outline: none;
  font-size: 14px;
  font-weight: 700;
  color: #fff;
  cursor: pointer;
  transition: all 0.3s ease;
}

button:hover {
  background-color: #70a66f;
}

.flip-enter-active {
  transition: all 0.4s ease;
}

.flip-leave-active {
  display: none;
}

.flip-enter-from,
.flip-leave-from {
  transform: rotateY(180deg);
  opacity: 0;
}
@media only screen and (min-width: 1000px) {
  .displayCards {
    width: 70%;
    margin: auto;
  }
  ul {
    display: inline-flex;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
  }
  .card {
    display: block;
    margin: 20px;
  }
}
</style>
