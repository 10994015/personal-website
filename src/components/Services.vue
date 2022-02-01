<script>
import {reactive} from "vue";
export default {
    setup(){
        const services = reactive([
            {title:"Web Design",class:"fas fa-paint-brush",content:""},
            {title:"Website setup",class:"fas fa-chart-line",content:""},
            {title:"Artificial intelligence",class:"fas fa-code",content:""},
        ])
        return {services};
    }
}
</script>
<template>
  <section class="services" id="services">
        <div class="max-width">
            <div class="title">
                <h2>My services</h2>
            </div>
            <div class="services-content">
                <div class="card" v-for="item in services">
                    <div class="box">
                        <i :class="item.class"></i>
                        <div class="text">{{item.title}}</div>
                        <p>{{item.content}}</p>
                    </div>
                </div>
                
            </div>
        </div>
    </section>
</template>

<style scoped>
.services, .works{
    color:#fff;
    background-color: #111;
}
.services .title::before,
.works .title::before{
    background: #fff;
}
.services .title::after,
.works .title::after{
    background-color: #111;
    content: 'what i provide';
}
.services .services-content .card{
    width:calc(33% - 20px);
    background-color: #222;
    text-align: center;
    border-radius: 6px;
    padding: 20px 25px;
    cursor: pointer;
    transition: color .3s ease;
}
.services .services-content .card i{
    font-size: 50px;
    color:var(--main-color);
    
}
.services .services-content .card .box{
    transition: all .3s ease;
}
.services .services-content .card:hover{
    background: var(--main-color);
}
.services .services-content .card:hover i{
    color:#fff;
}
.services .services-content .card:hover .box{
    transform: scale(1.05);
}
.services .services-content .card .text{
    font-size: 25px;
    font-weight: 500;
    margin:10px 0 7px 0;
}
@media (max-width:950px){
    .services .services-content .card{
        width:calc(50% - 10px);
        margin-bottom: 20px;
    }
}
@media (max-width:690px){
    .services .services-content .card{
        width:100%;
    }
}
</style>
