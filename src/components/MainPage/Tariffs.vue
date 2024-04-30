<script setup>
import { onMounted, ref } from 'vue';
import Tariff from './Tariff.vue';

const tariffs = ref([
    {
        title: 'Совместная работа +',
        oldPrice: 1200,
        newPrice: 990
    },
    {
        title: 'Совместная работа: Бизнес',
        oldPrice: 1300,
        newPrice: 1100
    },
    {
        title: 'CRM: Клиенты и продажи +',
        oldPrice: 1400,
        newPrice: 1200,
        isBestChoise: true
    },
    {
        title: 'CRM: Бизнес',
        oldPrice: 1800,
        newPrice: 1500
    },
])

onMounted(()=> {
    const tariffButtons = document.querySelectorAll('.tariffs__button')

    function removeActiveClass () {
        tariffButtons.forEach(button => button.classList.remove('active'))
    }

    tariffButtons.forEach(button => {
        button.addEventListener('click', (e)=>{
            e.stopPropagation()
            if(!button.classList.contains('active')) {
                removeActiveClass()
                button.classList.add('active')
            }
        })
    })
})

</script>
<template>
    <section class="tariffs">
        <div class="container">
            <h2 class="section__title">Тарифы</h2>
            <div class="tariffs__buttons">
                <button class="tariffs__button active">Месяц</button>
                <button class="tariffs__button">3 Месяца <span class="discont"> - 10% скидка</span></button>
                <button class="tariffs__button">Год <span class="discont">- 15% скидка</span></button>
            </div>
            <div class="tariffs__wrapper">
                <Tariff 
                v-for="(item, index) in tariffs"
                :key="index"
                :title="item.title"
                :newPrice="item.newPrice"
                :oldPrice="item.oldPrice"
                :isBestChoise="item.isBestChoise"/>
            </div>
        </div>
    </section>
</template>
<style lang="sass" scoped>
.section__title
    margin-bottom: 20px
.tariffs__buttons
    display: flex
    border: 1px solid var(--border)
    border-radius: 10px
    padding: 6px 16px
    width: fit-content
    margin: 0 auto 30px auto
.tariffs__button
    border: none
    background: transparent
    color: var(--black)
    padding: 8px 19px
    border-radius: 10px
    font-family: 'Jost', sans-serif
    font-size: 15px
    font-weight: 500

    &.active
        background: var(--dark-blue)
        color: #fff
.tariffs__wrapper
    display: grid
    grid-template-columns: repeat(4, 1fr)
    gap: 20px
.discont
    pointer-events: none
@media(max-width:1100px)
    .tariffs__wrapper
        grid-template-columns: 1fr 1fr
@media(max-width:750px)   
    .tariffs__wrapper
        grid-template-columns: 1fr
    .tariffs__button
        padding: 1px 19px
        font-size: 14px
        display: flex
        flex-direction: column
        justify-content: center
        text-align: left
    .discont
        font-size: 10px
</style>