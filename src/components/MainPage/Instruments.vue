<template>
    <section class="instruments">
        <div class="container">
            <h2 class="section__title">Получите четкое представление о финансах вашего бизнеса</h2>
            <div class="wrapper">
                <div class="content">
                    <h3 class="title">Облачная CRM</h3>
                    <p class="description">Предложите своим клиентам лучший сервис и упростите работу отдела продаж. CRM-система — это решение проблемы с утерянными контактами и хаосом в сделках. Приведите продажи в порядок и сделайте общение с клиентами удобным с функционалом.</p>
                    <div class="buttons">
                        <div class="buttons">
                        <button class="btn ">Начать бесплатно</button>
                        <button class="btn btn_white">Войти</button>
                    </div>
                    </div>
                </div>
                <div class="img"><img src="/instrument-1.png" alt=""></div>
            </div>
            <div class="wrapper">
                <div class="content">
                    <h3 class="title">Управление проектами</h3>
                    <p class="description">Система помогает удобно вести проекты, следить за дедлайнами, исполнителями, взаимодействовать с заказчиками. Начинайте работу в два клика с помощью шаблона и наблюдайте за прогрессом на канбан-доске.</p>
                    <div class="buttons">                        
                        <button class="btn ">Начать бесплатно</button>
                        <button class="btn btn_white">Войти</button>                   
                    </div>
                </div>
                <div class="img"><img src="/instrument-2.png" alt=""></div>
            </div>
        </div>
    </section>
</template>

<style lang="sass" scoped>
.instruments
    margin-bottom: clamp(80px, 19vw, 105px)
.wrapper
    display: flex
    justify-content: space-between
    align-items: center
    margin-bottom: 100px

    &:nth-of-type(2)
        margin-bottom: 0
        .content
            order: 2
        .img
            order: 1
.content
    width: 41%
.title
    font-family: 'Jost', sans-serif
    margin-bottom: 30px
    font-weight: 500
    line-height: 105%
    font-size: clamp(20px, 4vw, 24px)

.description 
    margin-bottom: 30px
    color: var(--gray)

.buttons 
    display: flex
    gap: 10px    

    .btn       
        width: 201px
    .btn_white        
        width: 190px

@media(max-width:1000px)
    .wrapper
        flex-direction: column
        align-items: start
        gap: 30px
        margin-bottom: 60px
        
        &:nth-of-type(2)
            margin-bottom: 0
            .content
                order: 1
            .img
                order: 2
    .content
        width: 100%     

@media(max-width:500px)    
    .buttons
        flex-direction: column
        .btn
            width: 100%
            height: 50px
</style>