<template>
  <div class="header">
    <h1>ToDo List</h1>
  </div>
  <todo-input @addTodo="addTodoItem"></todo-input>
  <todo-list :todoItem="todoItem"></todo-list>
  <todo-footer></todo-footer>
  <!-- {{todoItem}} -->

</template>

<script>
import TodoFooter from './components/TodoFooter.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
export default {
  components: { TodoInput, TodoList, TodoFooter },
  data(){
    return{
      todoItem:[]
    }
  },

  methods:{
    addTodoItem(item){
      console.log("할일추가" + item)
      this.todoItem.push(item)
    }
  }


}
</script>


<style>
@import url('./assets/reset.css');
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
body{
  font-family: 'Roboto', sans-serif;
}
#app{
  width: 400px;
  margin: 0 auto;
  _background: skyblue;
}
</style>
