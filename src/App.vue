<template>
<div class="visual">
        <div class="visualWrap">
            <div class="hearder">
                <div class="titleWrap">
                    <h2>Todo List</h2>
                    <p>할 일을 작성하세요!</p>
                </div>
                <div class="timg"><img src="./assets/title_img.png" alt=""></div>
            </div>
           
              <todo-input @addTodo="addTodoItem"></todo-input>
              
              <todo-list :todoItem="todoItem" @reDel="removeDel"></todo-list>
              <todo-footer @clearAll="clearAll"></todo-footer>
              
                        <!-- 에밋 신호를 받는다 -->
              <!-- {{todoItem}} -->
           
        </div>
</div>        
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


<style lang="scss">
@import url('./assets/reset.css');
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
html{height: 100%;}
body{
  font-family: 'Roboto', sans-serif; height: 100%; 
  display: flex; align-items: center; justify-content: center;
  background-color: #eee;
}
.visual{
    width: 100%; height: 100%;
  .visualWrap{
    margin: 0 auto;
    width: 360px;
    height: 640px;
    background: #032E53;
    border-radius:20px; 
    padding: 20px;
    .hearder{
      display: flex;
      padding: 20px 10px;
      .titleWrap{
        color: #eee;
        h2{
          font-weight: 700;
          font-size: 35px;
          line-height: 40px;
        }
        p{
          font-size: 14px;
          line-height: 30px;
          letter-spacing: -0.005em; 
        }
      }
      .timg{
        display: flex; align-items: flex-end;
        padding-left: 10px;
      }
    }  
  }
}





</style>
