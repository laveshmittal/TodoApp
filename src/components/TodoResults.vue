<template >
    <div v-if="todos.length">
        <ul>
            <li v-for="(todo,index) in todos" :key="index" @click="removeTodo(todo)">{{todo}}</li>
        </ul>
    </div>
    <div v-else> Empty List</div>
</template>
<script>
export default {
    methods: {
        removeTodo(todo){
            this.$emit('removeTodo',todo);
        },
    },
    props:['todos']    
}
</script>
<style >
    
</style>