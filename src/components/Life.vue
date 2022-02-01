

<script>
import {reactive} from "vue";
export default {
    props:{
        openImg:{
            type:Boolean,
            default:false,
        },
        openImgFn:{
            type:Function,
            default:()=>{},
        }
    },
    setup(props){
        const lifeImg = reactive([
            {src:"https://10994015.github.io/personal/images/life1.jpg"},
            {src:"https://10994015.github.io/personal/images/life2.jpg"},
            {src:"https://10994015.github.io/personal/images/life3.jpg"},
            {src:"https://10994015.github.io/personal/images/life4.jpg"},
            {src:"https://10994015.github.io/personal/images/life5.jpg"},
            {src:"https://10994015.github.io/personal/images/life6.jpg"},
            {src:"https://10994015.github.io/personal/images/life7.jpg"},
            {src:"https://10994015.github.io/personal/images/life8.jpg"},
            {src:"https://10994015.github.io/personal/images/life1.jpg"},
            {src:"https://10994015.github.io/personal/images/life2.jpg"},
            {src:"https://10994015.github.io/personal/images/life3.jpg"},
            {src:"https://10994015.github.io/personal/images/life4.jpg"},
            {src:"https://10994015.github.io/personal/images/life5.jpg"},
            {src:"https://10994015.github.io/personal/images/life6.jpg"},
            {src:"https://10994015.github.io/personal/images/life7.jpg"},
            {src:"https://10994015.github.io/personal/images/life8.jpg"},
        ])

        return {lifeImg, props};
    }
}
</script>
<template>
  <section class="life" id="life">
            <div class="max-width">
                <div class="title">My life</div>
                <div class="life-content">
                    <div class="photoBox">
                        <div v-for="item in lifeImg" class="photo">
                            <img :src="item.src" alt="" @click="props.openImgFn">
                        </div>
                        
                    </div>
                </div>
            </div>
        </section>
</template>
<style scoped>
.life .title::after{
    content:"My life record";
}
.life .life-content .photoBox{
    width:1205px;
    margin:auto;
    display: flex;
    overflow: hidden;
    border:5px solid var(--main-color);
    border-radius: 6px;
}
.life .life-content .photoBox .photo{
    width:300px;
    height: 300px;
    margin-right: 1px;
    animation: photo-move 20s infinite linear;
}
.life .life-content .photoBox .photo img{
    width:300px;
    height: 300px;
    object-fit: cover;
    cursor: pointer;
}
@keyframes photo-move{
    0%{
        transform: translateX(0);
    }
    100%{
        transform: translateX(-803%);
    }
    
}
@media (max-width:950px){
    .life .life-content .photoBox{
        width:605px;
    }
}
@media (max-width:690px){
    .life .life-content .photoBox{
        width:305px;
    }
}
@media (max-width:500px){
    .life .max-width{
      margin:auto;
       padding: 0 ;
   }
}
</style>