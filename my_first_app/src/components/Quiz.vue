<template>
<div>
    <div class="row">
        <div class="col-sm-6 offset-sm-3">
            <h1 class="text-center">Math Quiz</h1>

            <div class="quiz text-center">
                {{firstNumber}} + <input type="text" size=2 v-model="usersAnswer"> = {{answer}}
                <br>
                <button v-on:click="checkAnswer">Check Answer</button>
            </div>
            <div class="response-message text-center">{{responseMessage}}</div>
        </div>
    </div>
</div>
</template>

<script>
    export default {
        name: 'Quiz',
        data(){
            return {
                firstNumber: '2',
                answer: '4',
                secondNumber: '0',
                usersAnswer: '',
                responseMessage: ''
            }
        },
        methods: {
            generateNumbers(){
                this.firstNumber = Math.floor((Math.random()*10) + 1)
                this.answer = Math.floor((Math.random() * 20) + this.firstNumber)
                this.secondNumber = this.answer - this.firstNumber
            },
            checkAnswer(){
                if(this.secondNumber == this.usersAnswer){
                    this.responseMessage = "Correct"
                }else{
                    this.responseMessage = "Wrong"
                }
            }
        },
        mounted: function(){
            this.generateNumbers()
        }
    }
</script>

<style>
    .quiz{
        font-size: 25pt;
    }
</style>
