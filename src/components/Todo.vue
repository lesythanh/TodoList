 <template>
 <div class="Todo">
  <div >
    <input type="checkbox" v-model="taskData.done">  
    <span :class="{done: taskData.done}">{{taskData.content}}</span>
     </div>
      <button @click="removeTodo(index)">X</button>
 </div>

</template>

<script>
export default {
  props:{
        taskData:{
            type: Object,
            required: true
        },
        index:{
          type: Number
        }
    },
  name: 'Todo',
    data() {
        return {
             
        }
    },
    methods: {
      addTask(){
        this.$emit('add-Task')
      },
      removeTodo(){
        this.$emit('remove-todo',this.index)
      }
    }
   

}
</script>

<style>
.done{
  text-decoration: line-through;
}
</style>

