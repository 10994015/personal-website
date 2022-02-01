<script>
import {ref} from "vue";
export default {
    setup(){
        const openMenu = ref(false);
        const openMenuFn = ()=>{
            openMenu.value = !openMenu.value;
        }
        return {openMenu, openMenuFn};
    }
}
</script>
<template>
<header>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css">
    <a href="./" id="logo">LiChengYan</a>
    <nav :class="{active:openMenu}">
        <a href="#home">home</a>
        <a href="#about">about</a>
        <a href="#services">services</a>
        <a href="#skills">skills</a>
        <a href="#works">works</a>              
    </nav>       
    <div class="menu-btn" @click="openMenuFn">
        <i class="fas fa-bars" :class="{active:openMenu}"></i>
    </div>
</header>
</template>
<style scoped>
header{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: rgba(0, 0, 0, .7);
    padding: 25px 100px;
    transition: all .3s ease;
    z-index: 999;
}

header.sticky{
    background-color: rgba(0, 0, 0, 1);
    padding: 20px 80px;
}
header > #logo{
    color:#fff;
    font-style: italic;
    font-weight: 600;
    font-size: 24px;
}
header >nav{
    display: flex;
    list-style: none;
}
header >nav > a{
    color:#fff;
    margin-left:25px;
    font-size: 16px;
    text-transform:uppercase;
    text-align: center;
    font-family: 'Ubuntu', sans-serif;
    font-weight: 600;
}
header >nav > a:hover{
    color: var(--main-color);
    transition: .3s;
}
header .menu-btn{
    color:#fff;
    cursor: pointer;
    font-size: 27px;
    display: none;
}

@media (max-width:950px){
    header{
        padding: 25px 50px;
    }
    header.sticky{
        padding: 15px 40px;
    }
    header .menu-btn{
        display: block;
        z-index: 999;
    }
    header >nav{
        width: 100%;
        height: 100vh;
        position: fixed;
        top: 0;
        left: -100%;
        background-color: rgba(0, 0, 0, .8);
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        transition: all .3s ease;
    }
    header .menu-btn >i.active::before{
        content : "\f00d";
    }
    header >nav.active{
        left: 0;
    }
    header >nav > a{
        width: 100%;
        font-size: 25px;
        margin:20px 0;
        padding: 5px 0;
    }
   
   
}
</style>