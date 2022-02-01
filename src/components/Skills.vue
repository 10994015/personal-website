<script>
import {reactive} from "vue";
export default {
    setup(){
        const exp = reactive([
            {name:"中原大學碩士班"},
            {name:"憶旺智慧工程師"},
            {name:"中原大學程式設計講師"},
            {name:"Python程式設計家教"},
            {name:"中原大學多媒體程式設計助教"},
            {name:"中原大學Python程式設計助教"},
            {name:"Microsoft Python證照"},
            {name:"中原大學畢業專題第三名"},
            {name:"全國資訊研討會第五名"},
            {name:"中原大學優良課業守護天使"},
            {name:"李紹陽數學輔導老師"},
            {name:"三星samsung活動督導"},
        ])
        const skills = reactive([
            {name:"HTML",bars:"90%"},
            {name:"CSS",bars:"80%"},
            {name:"JavaScript",bars:"80%"},
            {name:"PHP",bars:"70%"},
            {name:"MySQL",bars:"70%"},
            {name:"Python",bars:"75%"},
        ])
        return {exp, skills };
    }
}
</script>
<template>
  <section class="skills" id="skills">
        <div class="max-width">
            <h2 class="title">My skills</h2>
            <div class="skills-content">
                <div class="column left">
                    <div class="text">
                        My creative skills & expriences.
                    </div>
                    <li v-for="item in exp">{{item.name}}</li>
                    <!-- <a href="#">Read more</a> -->
                </div>
                <div class="column right">
                    <div class="bars" v-for="item in skills">
                        <div class="infor">
                            <span>{{item.name}}</span>
                            <span>{{item.bars}}</span>
                        </div>
                        <div :class="['line', item.name]"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>

.skills .title::after{
    content: 'what i know';
}
.skills .skills-content .column{
    width:calc(50% - 30px);
}
.skills .skills-content .left .text{
    font-size: 25px;
    font-weight: 600;
    margin-bottom: 10px;
}
.skills .skills-content .left p{
    text-align: justify;
}
.skills .skills-content .left a{
    display: inline-block;
    background-color: var(--main-color);
    color:#fff;
    font-size: 18px;
    padding: 8px 16px;
    margin-top: 20px;
    border-radius: 6px;
    border: 2px solid var(--main-color);
    font-weight: 600;
    transition:  all .3s ease;
}
.skills .skills-content .left a:hover{
    color:var(--main-color);
    background: none;
}
.skills .skills-content .right .bars{
    margin-bottom: 15px;
}
.skills .skills-content .right .infor{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 5px;
}
.skills .skills-content .right span{
    font-weight: 600;
    font-size: 18px;
}
.skills .skills-content .right .line{
    height: 10px;
    width:100%;
    background-color: lightgray;
    position: relative;
    margin-top: 3px;
}
.skills .skills-content .right .line::before{
    content:'';
    position: absolute;
    height: 100%;
    left:0;
    top:0;
    background-color: var(--main-color);
}
.skills .skills-content .right .HTML::before{
    width:90%;
}
.skills .skills-content .right .CSS::before{
    width:80%;
}
.skills .skills-content .right .JavaScript::before{
    width:80%;
}
.skills .skills-content .right .PHP::before{
    width:70%;
}
.skills .skills-content .right .MySQL::before{
    width:70%;
}
.skills .skills-content .right .Python::before{
    width:75%;
}

@media (max-width:950px){
    .skills .skills-content .column{
        width:100%;
        margin-bottom: 35px;
    }
}
</style>