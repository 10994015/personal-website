<script>
import {ref} from "vue";
import Header from '@/components/Header.vue'
import Home from '@/components/Home.vue'
import About from '@/components/About.vue'
import Services from '@/components/Services.vue'
import Skills from '@/components/Skills.vue'
import Works from '@/components/Works.vue'
import Life from '@/components/Life.vue'
import LifeModel from '@/components/LifeModel.vue'
import Footer from '@/components/Footer.vue'
import Scroll from '@/components/Scroll.vue'

export default {
  components: {
    Header,
    Home,
    About,
    Services,
    Skills,
    Works,
    Life,
    LifeModel,
    Footer,
    Scroll,
  },
  setup(){
    window.addEventListener("scroll", function(){
      const header = document.querySelector("header");
      header.classList.toggle('sticky', window.scrollY > 0);
      const upBtn = this.document.getElementsByClassName('scroll-up-btn')[0];
      upBtn.classList.toggle('active', window.scrollY > 500);    
    });
    const modelsrc = ref("");
    const openImg = ref(false);
    const openImgFn = (e)=>{
        openImg.value = !openImg.value;
        modelsrc.value = e.target.src;
        
        
    }
    return {openImg, openImgFn,modelsrc};
  }
}
</script>
<template>
<Header />
<Home />
<About />
<Services />
<Skills />
<Works />
<Life  :openImgFn="openImgFn" />
<LifeModel :modelsrc="modelsrc" :openImgFn="openImgFn"  :openImg="openImg" />
<Footer />
<Scroll />
</template>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Ubuntu:ital,wght@0,300;1,300&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200&family=Ubuntu:ital,wght@0,300;1,300&display=swap');
:root{

	--main-color:#ffa600;
}
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Ubuntu', sans-serif;
    text-decoration: none;
    scroll-behavior: smooth;
}
a{
    color:#000;
    
}
.max-width{
    max-width: 1300px;
    margin:auto;
}
section{
    padding: 100px 0;
}
section .title{
    font-family: 'Ubuntu', sans-serif;
    font-size: 30px;
    text-align: center;
    font-weight: 500;
    margin-bottom: 40px;
    padding-bottom: 20px;
    position: relative;
}
section .title::before{
    content:'';
    position: absolute;
    width:180px;
    height: 3px;
    bottom: 0px;
    left:50%;
    background-color: #111;
    transform: translateX(-50%);
}
section .title::after{
    position: absolute;
    padding:5px;
    bottom: -12px;
    left:50%;
    font-size: 20px;
    background: #fff;
    transform: translateX(-50%);
    font-weight: 600;
    color:var(--main-color);
}
.about, .services, .skills, .works{
    font-family: 'Poppins', sans-serif;
}
.about .about-content,
.services .services-content,
.skills .skills-content
{
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
}
.skills .title,
.works .title,
.life .title{
    font-size: 50px;
    font-weight: 600;
}
@media (max-width:1300px){
   .max-width{
        padding: 0 80px;
    }
}
@media (max-width:950px){
    .max-width{
        max-width: 800px;
    }
}
@media (max-width:400px) {
  section .title::before{
    
    bottom: -10px;
    left:50%;
    
}
section .title::after{
    
    bottom: -40px;
    left:50%;
   
}
}
</style>
