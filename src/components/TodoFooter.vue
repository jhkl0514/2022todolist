<template>
 <div class="clearWrap">
   <div class="clearAll" @click="$emit('clearAll')">
    <!-- //신호를 보낸다 -->
    <i class="fa-solid fa-eraser"></i>&nbsp all
   </div>
  
 </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">

.clearWrap{
    display: flex;
    justify-content: center;
    .clearAll{
      display: flex;justify-content: center;align-items: center;
      background: #000;    
      color:rgb(255, 180, 42);   
      border-radius: 20px;
      font-size: 20px;
      padding: 10px 20px;
      cursor: pointer;
    }
  }
</style>