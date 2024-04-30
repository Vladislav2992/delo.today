<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const isDesktop = ref(window.innerWidth > 950);

const handleResize = () => {
    isDesktop.value = window.innerWidth > 950;
};

onMounted(() => {
    window.addEventListener('resize', handleResize);
});

onBeforeUnmount(() => {
    window.removeEventListener('resize', handleResize);
});
</script>

<template>
    <section class="hero">
        <div class="container">
            <div class="content">
                <h1 class="hero__title">Лучшая&nbsp;экосистема для&nbsp;вашего&nbsp;бизнеса</h1>
                <p class="description">Маркетинговая платформа, которая помогает привлекать больше трафика, увеличивать
                    конверсию в заявки, повышать продажи и лояльность клиентов</p>
                <img class="mobile" v-if="isDesktop === false" src="/main.png" alt="">
                <div class="buttons">
                    <button class="btn">Начать бесплатно</button>
                    <button class="btn btn_white">Войти</button>
                </div>
            </div>
            <div class="img" v-if="isDesktop">
                <img class="desctop" src="/main.png" alt="">
            </div>
            <img src="/circles.png" alt="" class="circles">
        </div>
            
    </section>
</template>

<style lang="sass" scoped>
.hero
    padding-top: 60px
    position: static
.circles
    position: absolute
    left: -59%
    top: -20px 
.container 
    position: relative
    display: grid
    grid-template-columns: 1fr 1fr
    align-items: center
    justify-content: center
    gap: 64px
    height: calc(100vh - 60px)

.hero__title 
    font-size: clamp(34px, 6vw, 64px)
    line-height: 105%
    font-family: 'Jost', sans-serif
    margin-bottom: clamp(15px, 3vw, 30px)
    font-weight: 500
.description   
    margin-bottom: 30px
    color: var(--gray)
.buttons 
    display: flex
    gap: 10px

    .btn
        width: 295px
    .btn_white
        width: 190px


@media (min-width:1920px)
    .circles
        top: 17%         

@media(max-width:1200px)
    .circles
        display: none         

@media(max-width:950px)
    .hero
        padding-top: 105px
    .container 
        height: auto
        grid-template-columns: 1fr
    .buttons
        flex-direction: column
        padding-top: 30px
        .btn
            width: 100% 
            height: 50px   
</style>