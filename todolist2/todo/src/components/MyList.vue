<template>
    <ul class="todo-main">
        <MyItem v-for="todoObj in todos" :key="todoObj.id" :todo="todoObj" :checkTodo="checkTodo"
            :deleteTodo="deleteTodo" />
    </ul>
</template>

<script>
import MyItem from './MyItem.vue'
export default {
    name: 'MyList',
    compenents: { MyItem },
    props: ['todos', 'checkTodo', 'deleteTodo']
}
</script>

<style>
</style>