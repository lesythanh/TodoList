<template>
  <div id="app">
      <input type="tex" v-model="newTask" >
    <button @click="addTask">Add</button>
    <button @click="removeTask(task)">Remove</button>
    <div v-for="(task, index) in tasks" :key="index">
    <input type="checkbox" v-model="task.done">  
    <span :class="{done: task.done}">{{task.content}}</span>
    </div>
<!-- <HelloWorld v-for="(task, index) in tasks" :key="index" :taskData="task"/> -->
</div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'App',
  data(){
    return{
      newTask: '',
      tasks: [
      ]
    }
  },
  methods: {
    addTask: function(){
      this.tasks.push({content: this.newTask, done: false});
    },
    removeTask: function(){
      this.tasks.filter({content: this.newTask, done: false});
      
    }
  },
  components: {
    // HelloWorld
  }
}
</script>

<style>
.done{
  text-decoration: line-through;
}
</style>
