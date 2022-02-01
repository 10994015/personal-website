<script>
export default {
    setup(){
        const top = ()=>{
            document.body.scrollTop = 0;
            document.documentElement.scrollTop = 0;
        }
        return {top, };
    }
}
</script>
<template>
  <div class="scroll-up-btn" @click="top" ref="scroll">
        <i class="fas fa-angle-up"></i>
    </div>
</template>

<style scoped>
.scroll-up-btn{
    position: fixed;
    height: 45px;
    width:45px;
    background-color: var(--main-color);
    right:-30px;
    bottom:30px;
    text-align: center;
    line-height: 45px;
    color:#fff;
    z-index: 9999;
    font-size: 30px;
    border-radius: 50%;
    cursor: pointer;
    opacity: 0;
    transition: .5s;
}
.scroll-up-btn.active{
    right:30px;
    opacity: 1;
}
</style>