<template>
    <div class="todo-footer" v-show="total">
        <label>
            <!-- <input type="checkbox" :checked="isAll" @change="checkAll"/> -->
            <input type="checkbox" v-model="isAll" />
        </label>
        <span>
            <span>CompletedTask{{ doneTotal }}</span>//AllTasks{{ total }}
        </span>
        <button class="btn btn-dager" @click="clearAll">ClearCompeletedTask</button>
    </div>
</template>

<script>
export default {
    name: "MyFooter",
    props: ['todos', 'checkAllTodo', 'clearAllTodo'],
    computed: {
        total() {
            return this.todos.length
        },
        doneTotal() {
            // let i = 0
            // this.todos.forEach((todo) => {
            //    if(todo.done) i++
            // })
            //  return i
            //////////////////////////////////////////
            // const x = this.todos.reduce((pre, current)=>{
            //     console.log('@', pre, current)
            //     return pre + (current.done ? 1 : 0)
            // },0)
            ////////////////////////////////////////////
            return this.todos.reduce((pre, todo) => pre + (todo.done ? 1 : 0), 0)
        },
        isAll: {
            get() {
                return this.doneTotal === this.total && this.total > 0
            },
            set(value) {
                this.checkAllTodo(value)
            }
        },
        methods: {
            checkAll() {
                this.checkAllTodo()
            }
        },
    }
}
</script>

<style>
</style>