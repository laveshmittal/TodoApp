<template>
<div class="root">
    <div>
            <label>New Todo</label>
          <input type="text" name="todo-input" id="todo-input" v-model="todo">  
          <br>
          <button @click="addTodo">Add ToDo</button>
        </div>
</div>
</template>
<script>
export default {
data(){
    return{
        todo:''
    }
},
methods:{
    addTodo(){
        if(!this.todo)return;
        this.$emit('addTodo',this.todo);
        this.todo = '';
    }
}    
}
</script>
<style scoped>

</style>
