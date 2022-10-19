<template>
<div class="searchInput">
    <input type="text" class="inp" placeholder="오늘의 할일을 입력하세요"
    v-model="newTodoItem">
    <div class="btn" @click="totoItem">할일</div>
    
</div>
<!-- {{newTodoItem}} -->

<transition name="mView">
    <Modal v-if="modalView" @click="modalView=false">
        <template v-slot:header>자료를 입력하세요.</template>
        <template v-slot:body>자료를 입력하세요.</template>
        <!-- slot을 통해서 자식에게 내용을 전송할 수 있다 -->
    </Modal>
</transition>
<!-- <Modal v-if="modalView" @modalClose="modalView=false" ></Modal> -->
</template>

<script>
import Modal from "@/components/Modal.vue"

export default {
    components: {Modal},

   data(){
    return{
        newTodoItem:'',
        modalView:false,
    }
   },
   methods:{
    totoItem(){
        if( this.newTodoItem != ""){
            let value = this.newTodoItem && this.newTodoItem.trim();
            //&& this.newTodoItem.trim() :공백 없애기
            // let value = this.newTodoItem;
            this.$emit("addTodo",value);
        }else{
            // alert("오늘의 할일을 입력하세요")
            this.modalView = true
        }
        this.newTodoItem =''
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

.mView-enter-from{opacity:0; transform: translateY(-100%);}
.mView-enter-active{transition: 0.3s;}
.mView-enter-to{opacity: 1; transform: translateY(0);}
//열릴때

.mView-leave-from{opacity:1}
.mView-leave-active{transition: 0.3s;}
.mView-leave-to{opacity: 0;}
//닫을때

</style>