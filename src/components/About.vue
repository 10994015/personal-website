<script>
export default {
    setup(){

        return {};
    }
}
</script>
<template>
<section class="about" id="about">
    <div class="max-width">
        <div class="title">
            <h2>About me</h2>
        </div>
    <div class="about-content">
            <div class="column left">
                <img src="@/assets/images/about.jpg" alt="" @click="openImgFn">
            </div>
            <div class="column right">
                <div class="text">I'm LiChengYan and I come from <span>Taoyuan</span></div>
                <p>姓名:李承諺(Li-Cheng-Yan)<br>生日:1997/08/22<br>中原大學研究所資管所(2020~2022)</p>
                <li>熱愛嘗試新的事物</li>
                <li>善於溝通和分享新知</li>
                <p>Mail : a0938599191@gmail.com</p>
                <a href="@/assets/li.pdf" download="li.pdf">Download CV</a>
            </div>
    </div>
    </div>
</section>
</template>

<style>

.about .title::after{
    content:'who i am';
}

.about .about-content .left{
    width: 45%;
}

.about .about-content .left img{
    width:400px;
    height: 500px;
    object-fit: cover;
    border-radius: 6px;
    cursor: pointer;
}
.about .about-content .right{
    width:55%;
    line-height: 1.8;
}
.about .about-content .right .text{
    font-size: 25px;
    font-weight: 600;
    margin-bottom: 10px;
}
.about .about-content .right .text span{
    color:var(--main-color);
}
.about .about-content .right p{
    text-align: justify;
    font-weight: 600;
    font-size: 18px;
}
.about .about-content .right a{
    display: inline-block;
    background-color: var(--main-color);
    color:#fff;
    font-size: 20px;
    padding: 10px 30px;
    margin-top: 20px;
    border-radius: 6px;
    border: 2px solid var(--main-color);
    font-weight: 600;
    transition:  all .3s ease;
}
.about .about-content .right a:hover{
    color:var(--main-color);
    background: none;
}

@media (max-width:950px){
    .about .about-content .column{
        width:100%;
    }
    .about .about-content .left{
        display: flex;
        justify-content: center;
        margin:0 auto 60px
    }
    .about .about-content .right{
        flex:100%;
    }
}
</style>