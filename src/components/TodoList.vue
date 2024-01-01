<template>
    <div>
        <TodoWord
            v-for="todo in todos" 
            :key="todo.id" 
            :todo="todo" 
            @toggle-checkbox="toggleCheckbox" 
            @click-delete="deleteTodo" 
        />
    </div>
</template>

<script>
import TodoWord from '@/components/TodoWord.vue';

export default {
    components: {
        TodoWord
    },
    props: {
        todos: {
            type: Array,
            required: true
        }
    },
    methods: {
        toggleCheckbox(value) {
            this.$emit('toggle-checkbox', value)
        },
        deleteTodo(todoId) {
            this.$emit('click-delete', todoId);
        }
    }

}
</script>

<style>

</style>