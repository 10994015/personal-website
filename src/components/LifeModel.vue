<script>
import {onUpdated, ref, watch} from "vue";
export default {
    props:{
        openImg:{
            type:Boolean,
            default:false,
        },
        modelsrc:{
            type:String,
            default:"./",
        },
        openImgFn:{
            type:Function,
            default:()=>{},
        }
    },
    setup(props){
        return {props, };
    }
}
</script>
<template>
<div class="life-model" v-show="props.openImg">
    <div class="lifeback" @click="props.openImgFn"></div>
    <img :src="props.modelsrc" alt="">
</div>
</template>
<style scpoed>
.life-model{
    position: relative;
    position: fixed;
    top: 0;
    left: 0;
    width:100%;
    height: 100vh;
    background-color: rgba(0, 0, 0, .5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 9999;
}
.life-model .lifeback{
    width: 100%;
    height: 100vh;
    position: absolute;
    top: 0;
    left: 0;
}
.life-model img{
    width:auto;
    max-height: 600px;
    border:5px #fff solid;
    z-index: 999;
    animation: mding .2s linear;
}
@keyframes mding{
    0%{
        transform: scale(0);
    }
    100%{
        transform: scale(1);
    }
}
</style>