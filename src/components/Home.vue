<script>
export default {
    setup(){
        const see = ()=>{
            document.body.scrollTop = 700;
            document.documentElement.scrollTop = 700;
        }
        return {see};
    }
}
</script>
<template>
  <section class="home" id="home">
            <div class="max-width">
               <div class="home-content">
                    <div class="text-1">Hello , my name is</div>
                    <div class="text-2">LiChengYan</div>
                    <div class="text-3">I come from <span>Taoyuan</span></div>
                    <a href="javascript:;" @click="see">See More</a>
               </div>
            </div>
        </section>
</template>

<style scoped>
.home{
    display: flex;
    background: url("~@/assets/images/bg.jpg") no-repeat;
    background-size:cover;
    background-position: left center;
    height: 100vh;
    color:#fff;
    font-family: 'Ubuntu', sans-serif;
}
.home .max-width{
    margin:auto 0 auto 120px;
}
.home .home-content .text-1{
    font-size: 27px;
}
.home .home-content .text-2{
    font-size: 70px;
    font-weight: 700;
    margin-left: -3px;
}
.home .home-content .text-3{
    font-size: 35px;
    margin:5px 0;
}

.home .home-content .text-3 span{
    color:var(--main-color);
    font-weight: 600;
}
.home .home-content a{
    display: inline-block;
    background-color: var(--main-color);
    color:#fff;
    font-size: 25px;
    padding: 12px 36px;
    margin-top: 20px;
    border-radius: 6px;
    border: 2px solid var(--main-color);
    font-weight: 600;
    transition:  all .3s ease;
}
.home .home-content a:hover{
    color:var(--main-color);
    background: none;
}
@media (max-width:1300px){
    .home .max-width{
       margin:auto 0 auto 50px;
   }
}
@media (max-width:1105px){
    .home .home-content a{
        font-size: 23px;
        padding: 10px 30px;
    }
}
@media (max-width:690px){
   
    .home .home-content .text-2{
        font-size: 60px;
      
    }
    .home .home-content .text-3{
        font-size: 32px;
    }
}
@media (max-width:500px){
    .home .home-content .text-2{
        font-size: 55px;
        margin-top: 12px;
      
    }
    .home .home-content .text-3{
        font-size: 27px;
        margin-top: 12px;
    }
    .home .home-content a{
        font-size: 20px;
        padding: 9px 25px;
    }
    .home .max-width{
       margin:auto 0 auto 0px;
       padding: 0 30px;
   }
}
</style>