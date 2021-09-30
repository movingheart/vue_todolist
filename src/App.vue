<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div class="container">
      <my-header :add="add"></my-header>
      <my-list :todos="todos" :delTodo="delTodo" :checkTodo="checkTodo"></my-list>
      <my-footer :todos="todos" :checkAll="checkAll" :clearAll="clearAll"></my-footer>
    </div>
  </div>
</template>

<script>
import {nanoid} from 'nanoid'
import MyHeader from "./components/MyHeader.vue";
import MyList from "./components/MyList.vue";
import MyFooter from "./components/MyFooter.vue";

export default {
  name: "App",
  components: {
    MyHeader,
    MyList,
    MyFooter,
  },
  data() {
    return {
      todos: [
        { id: "001", name: "吃饭", done: true },
        { id: "002", name: "睡觉", done: true },
        { id: "003", name: "打豆豆", done: false },
      ],
    };
  },
  methods:{
    add(e){
      console.log("data:", this.todos)
      this.todos.unshift({id: nanoid(), name: e.target.value, done: false})
      e.target.value=''
    },
    delTodo(id){
      this.todos = this.todos.filter((item)=>{return item.id !== id})
    },
    checkTodo(id){
      this.todos.forEach(item=>{
        if(item.id === id){
          item.done = !item.done
        }
      })
    },
    // checkAll(done){
    //   this.todos.forEach((item)=>{item.done = done})
    // }
    checkAll(e){
      this.todos.forEach((item)=>{item.done=e.target.checked})
    },
    clearAll(){
      this.todos = this.todos.filter((item)=>!item.done)
    }
  }
};
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

.container {
  width: 500px;
  height: auto;
  margin: 0 auto;
  border: 3px solid gray;
  border-radius: 5px;
}
</style>
