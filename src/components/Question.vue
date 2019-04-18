<template>
    <div class="hello">
        <h1>"Would you rather..."</h1>

        <p>
            {{question.question}}
        </p>
        <input type="radio" name="answer1" v-model="chan" v-on:change="this.$emit('answer', chan, questions.id)">{{question.answer1}}
        <input type="radio" name="answer2" v-model="chan" v-on:change="this.$emit('answer', chan, questions.id)">{{question.answer2}}

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
                chan: ''
            }
        },
        methods:{

        }
    }
</script>

<style scoped>

</style>