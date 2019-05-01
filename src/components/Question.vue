<template>
    <div class="hello">

        <p>
            {{question}}
        </p>
        <div v-if="id===0">
            <label >
                <input  type="radio" name="doot" v-bind:value="answer1" v-on:change="chosen(answer1,id)">{{answer1}}
            </label>
            <label>
                <input type="radio" name="doot" v-bind:value="answer2" v-on:change="chosen(answer2,id)">{{answer2}}
            </label>
        </div>
        <div v-if="id===1">
            <label >
                <input  type="radio" name="nDooDooDooDoooo" v-bind:value="answer1" v-on:change="chosen(answer1,id)">{{answer1}}
            </label>
            <label>
                <input type="radio" name="nDooDooDooDoooo" v-bind:value="answer2" v-on:change="chosen(answer2,id)">{{answer2}}
            </label>
        </div>
        <div v-if="id===2">
            <label >
                <input  type="radio" name="aaAAAaaaahhhhh" v-bind:value="answer1" v-on:change="chosen(answer1,id)">{{answer1}}
            </label>
            <label>
                <input type="radio" name="aaAAAaaaahhhhh" v-bind:value="answer2" v-on:change="chosen(answer2,id)">{{answer2}}
            </label>
        </div>

    </div>



</template>

<script>
    export default {
        name: "Question",
        props:{
            question: String,
            answer1: String,
            answer2: String,
            id: Number,
        },
        data(){
            return{

            }
        },
        methods:{
            chosen(answer, id){
                this.$emit('answer',answer, id)
            }
        }
    }
</script>

<style scoped>
</style>