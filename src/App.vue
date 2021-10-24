<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <p v-if="seen">
      {{message}}
    </p>
    <input type="text" v-model="message"><br>
    <button v-on:click="bbb">反转文字</button>
    <ul>
      <li :key="aaa" v-for="(todo,aaa) in todos">
        {{todo.text}}
      </li>
    </ul>
    <div v-bind:class="classObject">aaaaaaaa</div>
  </div>
  
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return{
      message:"杨臭臭大坏蛋！！！！",
      seen:true,
      todos:[
        {text:'学习 JavaScript'},
        { text: '学习 Vue' },
        { text: '整个牛项目' }
      ],
      isActive: true,
      error: null
    }  
  },
  methods:{
    bbb:function () {
      this.message = this.message.split('').reverse().join('')
    }
  },
  computed: {
  classObject: function () {
    return {
      active: this.isActive && !this.error,
      'text-danger': this.error && this.error.type === 'fatal'
    }
  }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
