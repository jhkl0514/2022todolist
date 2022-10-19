<template>
<!-- {{todoItem}} -->
<ul>
    <li v-for="(item,i) in todoItem" :key="i" class="itemList">
       <div class="list">
            <i class="fa-regular fa-square-check"></i>{{item}}
        </div>
       <div class="del" @click="removeDel(i,item)">
        <!-- //데이터 두개 넣음 -->
            <i class="fa-solid fa-trash-can"></i>
       </div>
    </li>   
</ul>
</template>

<script>
export default {
    props:[
        "todoItem"
    ],
    //메소드스에서 자료를 보낸다.($emit) 속성값으로 처리 가능(함수들어올수 있음)
    methods:{
        removeDel(num,item){
            this.$emit("reDel",num,item)
            // num 어레이 ,item 로컬스토리지
        }
    }

}
</script>

<style lang="scss">
.itemList{
    display: flex;
    justify-content:space-between;
    align-items: center;
    height: 35px;
    _background: pink;
    margin-bottom: 10px;
    .list{
        display: flex;
        gap:10px;
    }
    .del{
        background: skyblue;
        padding: 0 20px;
        height: 100%;
        cursor: pointer;
        align-self: start;
        display: flex;
        justify-content: center;
        align-items: center;
    }
}

</style>