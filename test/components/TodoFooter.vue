<template>
 <div class="clearAll" @click="$emit('clearAll')">
  <!-- //신호를 보낸다 -->
  clearAll
 </div>
</template>

<script>
export default {

}
</script>

<style>
  .clearAll{
    display: flex;justify-content: center;align-items: center;
    background: gray;
    color:white;
    height: 35px;
    border-radius: 10px;
    cursor: pointer;
  }
</style>