<template>
  <div id="app">
<todo-list />

</div>

</template>

<script>
import TodoList from './components/TodoList.vue'
export default {
  name: 'App',
   
  data(){
     return{
      // newTask: '',
      // tasks: [
      // ]
    }
   },
   methods:{
   
   },
  components:{
    TodoList
  }
  }
  
</script>

<style>

</style>
