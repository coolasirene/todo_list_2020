<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" placeholder="Please write the name of the participant" v-on:keypress.enter="addTodo">
        <span class="addContainer" v-on:click="addTodo">
            <i class="addBtn fas fa-plus" aria-hidden="true"></i>
        </span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTodoItem: ''
        }
    },
    methods: {
        addTodo() {
            if (this.newTodoItem !== "") {
                var value = this.newTodoItem && this.newTodoItem.trim()
                this.$emit('addTodo', value)
                this.clearInput()
            }
        },
        clearInput() {
            this.newTodoItem = ''
        }
    }
}
</script>

<style>
input:focus{outline:none}
.inputBox{height:5rem;padding-left:.9rem;border-radius:.5rem;line-height:.5rem;background-color:#fff;text-align:left}
.inputBox input{width:calc(100% - 3rem);height:5rem;padding:0;border-style:none;font-size:1.5rem;line-height:.5rem}
.addContainer{float:right;display:block;width:3rem;border-radius:0 .5rem .5rem 0;line-height:5rem;background:linear-gradient(to right, #6478fb, #8763fb);text-align:center}
.addBtn{color:#fff;vertical-align:middle}
</style>