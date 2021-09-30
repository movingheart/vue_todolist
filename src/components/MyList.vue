<template>
    <div class="list">
        <ul v-for="item in todos" :key="item.id">
            <my-item :item="item" :delTodo="delTodo" :checkTodo="checkTodo"></my-item>
        </ul>
    </div>
  
</template>

<script>
import MyItem from './MyItem.vue'

export default {
    name: 'MyList',
    components: {MyItem},
    props:['todos', 'delTodo', 'checkTodo']
}
</script>

<style>

</style>