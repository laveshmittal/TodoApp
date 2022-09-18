<template >
      <h2>ToDo Lists</h2>
    <div v-if="todos.length">
        <ul>
            <li v-for="(todo,index) in todos" :key="index" >
            <span>{{todo}}</span>
            <button @click="removeTodo(todo)">Remove</button>    
            </li>
        </ul>
    </div>
    <div v-else class="empty-list"> Empty List</div>
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
    h2{
        font-size: 22px;
    border-bottom: 2px solid hsla(0,0%,100%,.35);
    padding-bottom: 6px;
    }

    div.empty-list{
    text-align: center;
    opacity: .5;
    margin: 0;
    }
ul{
    list-style-type: none;
    margin: 0;
    padding: 0;
}
    li{
        display: flex;
    justify-content: space-between;
    align-items: center;
    border: 2px solid hsla(0,0%,100%,.35);
    padding: 12px 24px;
    border-radius: 6px;
    margin-bottom: 12px;
    box-sizing: border-box;
    
    }
    button{
    font-size: 12px;
    padding: 8px;
    cursor: pointer;
    background-color: rgb(61, 61, 224);
    border: 1px solid rgb(61, 61, 224);
    color: white;
    font-weight: 700;
    outline: none;
    border-radius: 6px;
    }
</style>