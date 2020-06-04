<template>
    <section>
        <transition-group name="list" tag="ul">
            <li v-for="(todoItem, index) in propsdata" :key="todoItem" class="shadow">
                <i class="checkBtn fas fa-check" aria-hidden="true"></i>
                {{ todoItem }}
                <span class="removeBtn" type="button" @click="removeTodo(todoItem, index)">
                    <i class="far fa-trash-alt" aria-hidden="true"></i>
                </span>
            </li>
        </transition-group>
    </section>
</template>

<script>
export default {
    props: ['propsdata'],
    methods: {
        removeTodo(todoItem, index) {
            this.$emit('removeTodo', todoItem, index)
        }
    }
}
</script>

<style>
ul{list-style-type:none;padding-left:0;margin-top:0;text-align:left}
li{display:flex;height:5rem;margin:.5rem 0;padding:0 .9rem;line-height:5rem;background:#fff;border-radius:.5rem}
.checkBtn{color:#62acde;margin-right:.5rem;line-height:inherit}
.removeBtn{margin-left:auto;color:#de4343}
.list-enter-active,
.list-leave-active{transition:all 1s}
.list-enter,
.list-leave-to{opacity:0;transform:translateY(3rem)}
</style>