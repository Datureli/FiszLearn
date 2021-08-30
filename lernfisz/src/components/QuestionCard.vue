<template>
  <div>
      <div v-for="(question,index) in questions" :key="index" class="card">
          
        <h1>{{ question.question}}</h1>
        <p>question</p>
        <button>show answer</button>
      </div>
  </div>
</template>

<script>
export default {
data() {
    return {
        questions: [
            {
                question: 'Co to jest git?',
                answer: 'Git jest to rozproszony system kontroli wersji'
            },
              {
                question: 'Co to jest git?',
                answer: 'Git jest to rozproszony system kontroli wersji'
            },
              {
                question: 'Co to jest git?',
                answer: 'Git jest to rozproszony system kontroli wersji'
            },
              {
                question: 'Co to jest git?',
                answer: 'Git jest to rozproszony system kontroli wersji'
            }
        ]
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
}
</style>