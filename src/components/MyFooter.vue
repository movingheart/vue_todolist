<template>
  <div class="footer" v-show="total">
    <label>
      <input type="checkbox" :checked="isAll" @change="checkAll"/>
    </label>
    <span> 已完成{{doneCount}}/全部{{total}} </span>
    <button @click="clearAll">清除已完成</button>
  </div>
</template>

<script>
export default {
  name: "MyFooter",
  props:["todos", "checkAll", "clearAll"],
  computed:{
    doneCount(){
      return this.todos.filter((item)=>item.done).length
    },
    total(){
      return this.todos.length
    },
    isAll(){
      return this.doneCount == this.total && this.total > 0
    }
  }
};
</script>

<style>
.footer button{
  float: right;
}
</style>