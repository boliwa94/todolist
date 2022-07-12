<template>
    <li>
        <label>
            <input type="checkbox" :checked="todo.done" @change="handleCheck(todo.id)" />
            <span>{{ todo.title }}</span>
        </label>
        <button class="btn btn-danger" @click="handleDelete(todo.id)">del</button>
    </li>
    <!-- <li>
        <label>
            <input type="checkbox" />
            <span>//////////</span>
        </label>
        <button class="btn btn-danger" style="display:none">del</button>
    </li>
    <li>
        <label>
            <input type="checkbox" />
            <span>----------</span>
        </label>
        <button class="btn btn-danger" style="display:none">del</button>
    </li> -->
</template>

<script>
export default {
    name: 'MyItem',
    props: ['todo', 'checkTodo', 'deleteTodo'],
    methods: {
        handleCheck(id) {
            this.checkTodo(id)
        },
        handleDelete(id) {
            if (confirm('Comfirm delete')) {
                this.deleteTodo(id)
            }
        }
    },
}
</script>

<style>
</style>