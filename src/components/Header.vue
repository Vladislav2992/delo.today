<script setup>
import { ref, onMounted } from "vue"

const isMobileMenuOpen = ref(false)

const openMobileMenu = () =>{
    const body = document.querySelector('body')
    if(isMobileMenuOpen.value === false) {
        isMobileMenuOpen.value = true
       body.classList.add('disabled')
    } else {
        isMobileMenuOpen.value = false
        body.classList.remove('disabled')
    }
}

onMounted(() => {
    const menuList = document.querySelectorAll('.with-children')   
    if (window.innerWidth < 950) {
        menuList.forEach(item => {
            item.addEventListener('click', () => {
                const subMenu = item.querySelector('.children-wrapper')

                if (item.classList.contains('active') && subMenu !== null) {
                    subMenu.style.maxHeight = '0'
                    item.classList.remove('active')
                } else {
                    subMenu.style.maxHeight = '1000px'
                    item.classList.add('active')
                }
            })
        })
    }
})
</script>
<template>
    <header class="header">
        <div class="container">
            <div class="logo"><router-link to="/">delo</router-link></div>
            <nav :class="['menu', {'active' : isMobileMenuOpen}]">
                <ul class="menu-list">
                    <li class="menu-item with-children"><a href="#!">Продукт</a>
                        <div class="children-wrapper">
                            <ul class="children-menu">
                                <li class="about"><a href="#!">О нас</a></li>
                                <li><a href="#!">Почему data.today?</a></li>
                                <li><a href="#!">Интеграции</a></li>
                                <li><a href="#!">Облоко или коробка</a></li>
                            </ul>
                            <ul class="children-menu">
                                <li class="more"><a href="#!">Дополнительно</a></li>
                                <li><a href="#!">Мобильное приложение</a></li>
                                <li><a href="#!">База знаний</a></li>
                            </ul>
                        </div>
                    </li>
                    <li class="menu-item with-children"><a href="#!">Решения</a>
                        <div class="children-wrapper">
                            <ul class="children-menu">
                                <li class="solutions"><a href="#!">Решения</a></li>
                                <li><a href="#!">Организация продаж</a></li>
                                <li><a href="#!">Управление проектами</a></li>
                                <li><a href="#!">Контроль задач</a></li>
                            </ul>
                            <ul class="children-menu">
                                <li class="tariffs"><a href="#!">Тарифы</a></li>
                                <li><a href="#!">Цены</a></li>
                                <li><a href="#!">Клиенты и продажи</a></li>
                            </ul>
                        </div>
                    </li>
                    <li class="menu-item"><a href="#!">Отзывы</a></li>
                    <li class="menu-item"><a href="#!">Кейсы</a></li>
                </ul>

                <div class="buttons">
                    <button class="btn">Начать бесплатно</button>
                    <button class="btn btn_white">Войти</button>
                </div>
            </nav>
            <div class="burger" @click="openMobileMenu">
                <img :src="isMobileMenuOpen ? '/close.svg' : '/burger.svg'" alt="">
            </div>
        </div>
        <div class="overlay" v-if="isMobileMenuOpen"></div>
    </header>
</template>
<style lang="sass" scoped>
.header 
    padding: 11px 0
    box-shadow: 0 2px 15px rgba(0,0,0, .05)
    position: fixed
    top: 0
    left: 0
    right: 0
    z-index: 10
    background: #fff

    .container
        display: grid
        grid-template-columns: 1fr 11fr
        align-items: center 

.logo
    font-family: 'Josefin Sans', sans-serif
    font-weight: 600
    font-size: 28px
    margin-right: 75px

.menu
    display: flex
    justify-content: space-between
    align-items: center 
    font-size: 15px
    font-weight: 500
    line-height: 130%

.menu-list
    display: flex
    gap: 60px

.with-children
    position: relative

    &::before
        content: ''
        position: absolute
        width: 100%
        height: 40px
        top: 100%
        visibility: hidden

    &:hover .children-wrapper
        opacity: 1
        visibility: visible
    &:hover:before
        visibility: visible
    &:hover:after
        transform: rotate(180deg)        
        
.with-children 
    position: relative
    padding-right: 22px

    &::after
        content: ''
        position: absolute
        width: 12px
        height: 7px
        right: 0
        top: 50%
        transform: translateY(-50%)
        background: url('../assets/img/dropdown-arrow.svg')
        transition: transform .2s
        transform-origin: 50% 20%

.children-wrapper
    box-shadow: 0 4px 20px 0 rgba(0, 0, 0, 0.15)
    background: #fff
    border-radius: 10px
    z-index: 2
    position: absolute
    display: flex
    padding: 25px 20px
    gap: 25px
    top: calc(100% + 31px)
    opacity: 0
    visibility: hidden
    

.children-menu
    display: flex
    flex-direction: column
    li
        display: inline-block
        color: var(--gray)
        padding-left: 36px
        font-weight: 400
        margin-bottom: 15px
        width: max-content
        transition: color .3s

        &:last-child
            margin-bottom: 0

        &:hover
            color: #9C88FF

    .about,
    .more,
    .solutions,
    .tariffs
        position: relative
        font-size: 16px
        color: var(--black)

        &:hover
            color: inherit

        &::before
            content: ''
            position: absolute
            top: -6px
            left: 0
            width: 26px
            height: 39px

.about::before
    background: url('../assets/img/box.svg') no-repeat center
.more::before
    background: url('../assets/img/dots.svg') no-repeat center
.solutions::before
    background: url('../assets/img/list.svg') no-repeat center
.tariffs::before
    background: url('../assets/img/tariffs.svg') no-repeat center


.buttons 
    display: flex
    gap: 15px
.burger
    margin-left: auto
    display: none
@media(max-width: 950px)
    .header
        padding: 12px 0
        position: relative        

        &::after
            content: ''
            position: absolute
            bottom: 0
            left: 0
            right: 0
            height: 1px
            box-shadow: 0 2px 15px rgba(0,0,0, .05)        

    .menu
        position: absolute     
        background: #fff
        flex-direction: column
        top: 48px
        left: 0
        right: 0
        padding: 30px 15px
        z-index: 11
        transform: translateX(120%)
        visibility: hidden
        transition: transform .3s

        &.active
            transform: translateX(0)
            visibility: visible
            

    .menu-list
        flex-direction: column
        width: 100%
        gap: 0
    .menu-item
        padding-bottom: 20px
        margin-bottom: 20px
        border-bottom: 1px solid #90e0ef

    .with-children
        padding-right: 0

        &::after
            transform: rotate(-90deg)
            top: 8px
        &::before
            content: none
        
        &:hover:after
            transform: rotate(-90deg)  

        &.active:after
            transform: rotate(-270deg)

    .children-wrapper
        position: static
        padding: 0
        width: 100%
        opacity: 1
        visibility: visible
        box-shadow: none
        border-radius: 0
        flex-direction: column
        gap: 0
        max-height: 0
        overflow: hidden
        transition: max-height .5s
    .children-menu
        border-top: 1px solid #90e0ef
        margin-top: 20px
        padding-top: 20px
        li
            padding: 0
            position: static  

        .about,
        .more,
        .solutions,
        .tariffs 
            &::before
                content: none 
    .buttons
        flex-direction: column
        width: 100%
        gap: 10px
        .btn
            width: 100%
            height: 45px
    .burger
        display: block
    .overlay 
        position: fixed
        top: 48px
        right: 0
        bottom: 0
        left: 0
        background: rgba(0, 0, 0, 0.5)
        z-index: 8
</style>