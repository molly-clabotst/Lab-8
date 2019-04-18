<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Question
            v-for="question in questions"
            v-bind:key="question.question"
            v-bind:question="question"
            v-on:answer="addToList"
    ></Question>

    <h1>You Would Rather...</h1>
      <ul>
          <li v-on:>{{questions[0].uAns}}</li>
          <li v-on:>{{questions[1].uAns}}</li>
          <li v-on:>{{questions[2].uAns}}</li>
      </ul>
<!--    <Choices v-bind:choice="choice"></Choices>-->
  </div>
</template>

<script>
import Question from "./components/Question";

export default {
  name: 'app',
  components: {
    Question,

  },
  data(){
    return{
        answer: '',
      questions:[
        {
          id: 0,
          question: 'be able to see things that are very far away,' +
                  ' like binoculars or be able to see things very close up,' +
                  ' like a microscope?',
          answer1: 'Binocular eyes',
          answer2: 'Scope eyes',
          uAns: ''
        },
        {
          id: 1,
          question: 'everything in your house be one color or' +
                  'every room be a different color?',
          answer1: 'Whole house',
          answer2: 'Only rooms',
          uAns: ''
        },
        {
          id: 2,
          question: 'be able to control fire or water?',
          answer1: 'Fire',
          answer2: 'Water',
          uAns: ''
        }
      ],
    }
  },
  methods:{
      addToList(anser, id){
          this.uAns = anser;
          this.questions[id].uAns.push(this.uAns);
      }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
