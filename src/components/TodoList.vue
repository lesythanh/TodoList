 <template>
 <div id="TodoList">
     <input type="tex" v-model="newTask" >
    <button @click="addTask" >Add</button>
    <todo v-for="(task, index) in tasks" :key="index" :taskData="task" :index="index"
        @add-Task="addTask" @remove-todo="removeTodo"/>
 </div>
  
</template>

<script>
import Todo from './Todo.vue'
export default {
    name: 'TodoList',
    data(){
   return{
       newTask: '',
      tasks: [
        {content: "học Java", done: false}
      ]
   }
  },
   methods: {
        addTask(){
      this.tasks.push({content: this.newTask, done: false});
    },
    removeTodo: function(index) {
      this.tasks.splice(index,1);
    }
   },
   components:{
    Todo
}
}
</script>

<style>

</style>
