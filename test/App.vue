//app

<template>
  <div class="header">
    <h1>ToDo List</h1>
  </div>
  <todo-input @addTodo="addTodoItem"></todo-input>
  <todo-list :todoItem="todoItem" @reDel="removeDel"></todo-list>
  <todo-footer @clearAll="clearAll"></todo-footer>
            <!-- 에밋 신호를 받는다 -->
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
  created(){
    for(let i=0; i<localStorage.lenght;i++){
      this.todoItem.push(localStorage.key(i))
    }
  },
  //초기데이터를 불러올때는 여기(created)에 꽂아줘야한다. 그리고 data에 넣는다.
  methods:{
    addTodoItem(item){
      // console.log("할일추가" + item);
      this.todoItem.push(item)
      localStorage.setItem(item,item)
      //데이터 받기 (item,item) key, value 로컬스토리지를 받아서 위에 데이터에 넣는다
    },
    removeDel(num,item){
      console.log(num + "신호잘받음");
      //todo리스트에서 인자값을 가져와야 한다.i
      this.todoItem.splice(num,1)
      localStorage.removeItem(item)
    },
    clearAll(){
      localStorage.clear();
      this.todoItem = [];
    },
  },
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
