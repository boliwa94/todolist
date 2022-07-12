<template>
    <div class="todo-header">
        <input type="text" placeholder="text your task" v-model="title" @keyup.enter="add" />
    </div>
</template>

<script>
import { nanoid } from 'nanoid'
export default {
    name: 'MyHeader',
    props: ['addTodo'],
    data() {
        return {
            title: ''
        }
    },
    methods: {
        add() {
            if (!this.title.trim()) {
                return alert("cant be null")
            }
            const todoObj = { id: nanoid(), title: this.title, done: false }
            this.addTodo(todoObj)
            this.title = ''
        }
    },
}
</script>

<style>
</style>