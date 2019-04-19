<template>
    <div class="hello">
        <h1>"Would you rather..."</h1>

        <p>
            {{question.question}}
        </p>
        <input type="radio" v-model="chan" v-bind:value="question.answer1" v-on:change="this.$emit('answer', chan, questions.id)">{{question.answer1}}
        <input type="radio" v-model="chan" v-bind:value="question.answer2" v-on:change="this.$emit('answer', chan, questions.id)">{{question.answer2}}

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