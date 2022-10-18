<template>
<div class="searchInput">
    <input type="text" class="inp" placeholder="오늘 할일"
    v-model="newTodoItem">
    <div class="btn" @click="todoItem">할일</div>
</div>
<!-- {{newTodoItem}} -->

</template>

<script>
export default {
   data(){
    return{
       newTodoItem:'' 
    }
   },
   methods:{
    todoItem(){
        // console.log("todoItem");
    this.$emit("addTodo",this.newTodoItem)    
    }
   }
}

</script>

<style lang="scss">
.searchInput{
    display: flex;
    .inp{
        flex: 1 0 auto;
        text-indent: 10px;
    }
    .btn{
        line-height: 40px;
        padding: 0 10px;
        background: gray;
        color: #fff;
        cursor:pointer;
    }
}
</style>