<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <h1>"Would you rather..."</h1>
        <Question
                v-for="question in questions"
                v-bind:key="question.question"
                v-bind:question="question.question"
                v-bind:answer1="question.answer1"
                v-bind:answer2="question.answer2"
                v-bind:id="question.id"

                v-on:answer="addToList"
        ></Question>

        <h1>You Would Rather...</h1>
        <ul>
            <li v-show="answered"> {{ans}}</li>
            <li v-show="answeredd">{{anss}}</li>
            <li v-show="answereddd">{{ansss}}</li>
        </ul>
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
                question:{},
                answered:false,
                answeredd:false,
                answereddd:false,
                ans:'',
                anss:'',
                ansss:'',
                questions:[
                    {
                        id: 0,
                        question: '...be able to see things that are very far away,' +
                            ' like binoculars or be able to see things very close up,' +
                            ' like a microscope?',
                        answer1: 'Binocular eyes',
                        answer2: 'Scope eyes',
                    },
                    {
                        id: 1,
                        question: '...have everything in your house be one color or' +
                            'every room be a different color?',
                        answer1: 'Whole house',
                        answer2: 'Only rooms',
                    },
                    {
                        id: 2,
                        question: '...be able to control fire or water?',
                        answer1: 'Fire',
                        answer2: 'Water',
                    }
                ],
            }
        },
        methods:{
            addToList(ans, id){
                if(id===0){
                    this.ans=ans;
                    this.answered=true;
                }else if (id===1) {
                    this.anss=ans;
                    this.answeredd=true;
                }else {
                    this.ansss=ans;
                    this.answereddd=true;
                }


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