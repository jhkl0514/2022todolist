<template>
<div class="modal">
    <h3>
        <slot name="header"></slot>
    </h3>
   <div class="linebar"></div>
    <p>
        <slot name="body"></slot>
    </p>
    <div>
        <button><i class="fa-solid fa-circle-xmark"></i></button>
    </div>
    <!-- <div>
        <button @click="$emit('modalClose')">닫기</button>
    </div> -->
  </div>
  
</template>

<script>
export default {

}
</script>

<style lang="scss">
.modal{
    width: 300px;
    height: 200px;
    background: #eee;
    position: fixed;
    left: 50%;
    top: 30%;
    margin-left: -150px;
    /* transform: translateX(-50%); TodoInput에서 Transform을 사용하기 때문에 뺏음 */
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap:20px;
    border-radius: 20px;
    box-shadow: 0 0 10px rgba(0,0,0,0.3);
    
    .linebar{
        width: 80%;
        height: 1px;
        background: rgb(202, 202, 202);

    }
    p{
        font-size: 14px;
    }
    i{
        font-size: 30px;
        color: #032E53;
        
    }
}

</style>