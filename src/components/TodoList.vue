 <template>
 <div id="todo-list">
   <h3 class="text-center"> To do App</h3>
     <form @submit.prevent>
        <input type="text"  placeholder="nhập dữ liệu vào đây" v-model="newTask">
        <button type="submit" @click ="addTask" >Add</button>
     </form>
      <todo v-for="(task, index) in tasks" :key="index" :taskData="task" :index="index"
      @remove-todo="removeTodo"/>
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
      this.newTask = ""
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
