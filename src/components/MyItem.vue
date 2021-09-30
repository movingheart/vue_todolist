<template>
    <!-- <li v-for="item in todos" :key="item.id"> -->
    <li >
        <label>
            <input type="checkbox" :checked="item.done" @change="checkTodo(item.id)"/>{{item.name}}
        </label>
        <button class="btn" @click="delTodo(item.id)">
            删除
        </button>
    
    </li>
  
</template>

<script>
export default {
    name: 'MyItem',
    props:["item", "delTodo", "checkTodo"],
}
</script>

<style>

    li{
        font-size: bold;
        list-style: none;
    }

    li input{
        margin-left: 0px;
        float: left;
    }

    li button{
        display: none;
        color: blue;
        float: right;
    }

    li:hover button{
        display: inline-block;
    }

</style>