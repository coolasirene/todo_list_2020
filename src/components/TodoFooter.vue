<template>
    <div class="clearAllContainer">
        <span class="clearAllBtn" @click="clearTodo">Clear All</span>
    </div>
</template>

<script>
export default {
    methods: {
        clearTodo() {
            this.$emit('removeAll')
        }
    }
}
</script>

<style>
.clearAllBtn{display:block;width:8.5rem;height:5rem;margin:0 auto;line-height:5rem;border-radius:.5rem;color:#e20303;background-color:#fff}
</style>