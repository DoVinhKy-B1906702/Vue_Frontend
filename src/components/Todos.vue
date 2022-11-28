<template>
  <TodoItem 
    v-for="todo in todos" 
    :key="todo.id" 
    :todoProps="todo" 
    @item-completed="markComplete"
    @delete-btn="deleteTodo"
  />
  
</template>

<script>
import { ref } from 'vue';
import TodoItem from './TodoItem';
export default {
    name:'TodosVue',
    components: {
      TodoItem
    },
    setup() {
      const todos = ref([
      {
        id: 1,
        title: 'Viec 1',
        completed:false,
      },
      {
        id: 2,
        title: 'Viec 2',
        completed: true,
      },
      {
        id: 3,
        title: 'Viec 3',
        completed:false,
      },
      ]);
      
      const  markComplete = id => {
        todos.value = todos.value.map(todo => {
          if( todo.id === id) todo.completed =  !todo.completed
          return todo;
        })
      }
      const  deleteTodo = id => {
        todos.value = todos.value.filter(todo => {
            return todo.id !== id ;
        }
        
        
        )
      }
      return {
        todos,
        markComplete,
        deleteTodo
      }
    },
    props: {
        description: String,
        name: String,
        address: String,
        
    }
}
</script>

<style>

</style>