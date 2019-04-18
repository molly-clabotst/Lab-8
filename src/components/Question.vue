<template>
    <div class="hello">
        <h1>"Would you rather..."</h1>

        <p>
            {{question.question}}
        </p>
        <input type="radio" name="answer1" v-model="change" v-on:change="this.$emit('answer', change, questions.id)">{{question.answer1}}
        <input type="radio" name="answer2" v-model="change" v-on:change="this.$emit('answer', change, questions.id)">{{question.answer2}}

    </div>



</template>

<script>

    export default {
        name: "Question",
        props:{
            question: Object
        },
        data(){
            return{
                change: ''
            }
        },
        methods:{

        }
    }
</script>

<style scoped>

</style>