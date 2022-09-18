<template>
<div class="root">
    <div>
          <label>New Todo</label>
          <br>
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
label{
    text-align: start;
    font-size: 14px;
    font-weight: 700;
    display: inline-block;
}
input{
    background-color: transparent;
    border: 2px solid hsla(0,0%,100%,.35);
    color: inherit;
    height: 48px;
    box-shadow: none;
    outline: none;
    padding-left: 12px;
    padding-right: 12px;
    border-radius: 6px;
    font-size: 18px;
    margin-top: 6px;
    margin-bottom: 12px;
    width: 100%;
    display: inline-block;
    box-sizing: border-box;
}
button{
      height: 48px;
    box-shadow: none;
    outline: none;
    padding-left: 12px;
    padding-right: 12px;
    border-radius: 6px;
    font-size: 18px;
    margin-top: 6px;
    margin-bottom: 12px;
    cursor: pointer;
    background-color: rgb(61, 61, 224);
    border: 1px solid rgb(61, 61, 224);
    color: white;
    font-weight: 700;
    width: 100%;
    }
</style>
