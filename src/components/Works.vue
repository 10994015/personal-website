<script>
import {reactive} from "vue";
export default {
    setup(){
        const worksCard = reactive([
            {imgsrc:"https://10994015.github.io/personal/images/9saio.jpg",
             href:"https://jiousaio.com/",
             title:"九霄空間設計JIOUSAIO",
             content:"幫助九霄空間設計公司架設公司形象網站",
            },
            {imgsrc:"https://10994015.github.io/personal/images/cst.png",
             href:"https://carboncst.com/",
             title:"臺灣碳材料學會CST",
             content:"為臺灣碳材料學會(CST)架設完整前後端網站",
            },
            {imgsrc:"https://10994015.github.io/personal/images/evone.jpg",
             href:"https://www.evoneic.com/",
             title:"憶旺智慧eVone",
             content:"為憶旺智慧架設公司形象網站",
            },
            {imgsrc:"https://10994015.github.io/personal/images/lecture.png",
             href:"https://jiousaio.com/Lecture/",
             title:"中原大學魷魚遊戲",
             content:"與中原大學衛保組合作，撰寫一套知識網頁遊戲",
            },
            {imgsrc:"https://10994015.github.io/personal/images/9.jpg",
             href:"https://jiousaioshop.com/",
             title:"九霄模型",
             content:"架設販賣模型的完整購物網站",
            },
            {imgsrc:"https://10994015.github.io/personal/images/colorful.jpg",
             href:"https://www.ice-finland.club/",
             title:"冰芬文教",
             content:"為冰芬文教補習班撰寫網頁前端",
            },
            
        ])
        return {worksCard};
    }
}
</script>
<template>
  <section class="works" id="works">
        <div class="max-width">
            <h2 class="title">My works</h2>
            <div class="carousel">
                <a v-for="item in worksCard" :href="item.href" class="card" >
                    <div class="box">
                        <img :src="item.imgsrc" alt="">
                        <div class="text">{{item.title}}</div>
                        <p>{{item.content}}</p>
                    </div>
                </a>
                
            </div>
        </div>
    </section>
</template>
<style scoped>
.works .title::after{
    content:'who with me';
}
.works .carousel{
    display: flex;
    flex-wrap: wrap;
}
.works .carousel .card{
    color:#fff;
    background-color: #222;
    border-radius: 6px;
    padding:25px 35px;
    width:calc(33% - 40px);
    text-align: center;
    margin:10px 20px;
    transition: all .3s ease;
    cursor: pointer;
}
.works .carousel .card:hover{
    background: var(--main-color);
}
.works .carousel .card .box{
    transition: all .3s ease;
}
.works .carousel .card:hover .box{
    transform: scale(1.05);
}
.works .carousel .card .text{
    font-size: 25px;
    font-weight: 600;
    margin:10px 0 7px 0;
}
.works .carousel .card img{
    height: 200px;
    width:200px;
    object-fit: cover;
    border-radius: 50%;
    border:5px solid var(--main-color);
    transition: all .3s ease;
}
.works .carousel .card:hover img{
    border-color:#fff;
}
@media (max-width:1105px){
    .works .carousel .card{
        width:calc(50% - 40px);
    }
}
@media (max-width:690px){
    .works .carousel .card{
        width:100%;
    }
}
@media (max-width:500px){
    .works .max-width{
        padding: 0px;
    }
    .works .carousel .card{
        width:90%;
    }
}
</style>