<template>

  <div id="app">
    <h1>Reactive Example</h1>
    Enter your name: <input type="text" v-model="name">
    <br>
    Hello, {{name}} {{message}}


    <br>
    <button v-on:click="btnClick">Click me</button>
    
  </div>
</template>

<script>
export default {
  name: 'app',
  data(){
    return {
      name: '',
      message: ''
    }
  },
  methods:{
    btnClick(){
      this.message = "Vue is Awesome!!"
    }
  }
}
</script>
