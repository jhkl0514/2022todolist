<template>
<div class="modal">
    <h3>
        <slot name="header"></slot>
    </h3>
    <p>
        <slot name="body"></slot>
    </p>
    <div>
        <button>닫기</button>
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

<style>
.modal{
    width: 300px;
    height: 200px;
    background: white;
    position: fixed;
    left: 50%;
    top: 10%;
    margin-left: -150px;
    /* transform: translateX(-50%); TodoInput에서 Transform을 사용하기 때문에 뺏음 */
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap:20px;
    border-radius: 20px;
    box-shadow: 0 0 10px rgba(0,0,0,0.3);
}

</style>