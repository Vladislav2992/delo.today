<template>
    <section class="about-product">
        <div class="container">
            <h2 class="section__title">Приведите продажи и задачи в порядок</h2>

            <div class="wrapper">
                <div class="content">
                    <h3 class="title">Облачная CRM</h3>
                    <p class="description">Предложите своим клиентам лучший сервис и упростите работу отдела продаж. CRM-система — это решение проблемы с утерянными контактами и хаосом в сделках. Приведите продажи в порядок и сделайте общение с клиентами удобным с функционалом.</p>

                    <div class="buttons">
                        <button class="btn btn_white">Начать бесплатно</button>
                        <button class="btn btn_transparent">Войти</button>
                    </div>
                </div>
                <img src="/finances.png" alt="">
            </div>
            <div class="wrapper">
                <div class="content">
                    <h3 class="title">Управление проектами</h3>
                    <p class="description">Система помогает удобно вести проекты, следить за дедлайнами, исполнителями, взаимодействовать с заказчиками. Начинайте работу в два клика с помощью шаблона и наблюдайте за прогрессом на канбан-доске.</p>
                    
                    <div class="buttons">
                        <button class="btn btn_white">Начать бесплатно</button>
                        <button class="btn btn_transparent">Войти</button>
                    </div>
                </div>
                <img src="/finances.png" alt="">
            </div>
        </div>
    </section>
</template>

<style lang="sass" scoped>
.wrapper 
    border-radius: 15px
    background: var(--dark-blue)
    margin-bottom: 50px
    color: #fff
    display: flex
    align-items: center
    padding: 93px 40px
    position: relative
    overflow: hidden
    height: 397px

    &:nth-of-type(1)
        .content              
            margin-right: auto
        img 
            right: -20px
            bottom: -23px
            border-radius: 15px 0 15px 0
        .title::before
            background: url('../../assets/img/coins.svg') no-repeat    

    &:nth-of-type(2)
        margin-bottom: 0
        .content                 
            margin-left: auto
        img 
            left: -20px
            bottom: -23px
            border-radius: 0 15px 0 15px
        .title::before
            background: url('../../assets/img/filters.svg') no-repeat    

.content 
    max-width: 50%
img
    position: absolute    
    width: 46%

.title
    padding-left: 38px
    font-family: 'Jost', sans-serif
    margin-bottom: 30px
    line-height: 105%
    font-size: clamp(20px, 4vw, 24px)
    position: relative

    &::before
        content: ''
        position: absolute
        left: 0
        top: 50%
        transform: translateY(-50%)
        width: 23px
        height: 23px

.description 
    margin-bottom: 30px
    color: #F8F8FD

.buttons 
    display: flex
    gap: 10px    

    .btn_white
        border-color: #fff
        width: 201px

        &:hover
            border-color: #3A3A3A
    .btn_transparent
        width: 190px
        &:hover
            border-color: #3A3A3A

@media(max-width:1100px)
    img
        width: 50%
@media(max-width:950px)
    .content
        max-width: 100%
        margin: 0
    .wrapper
        padding: 40px 20px
        flex-direction: column
        height: auto
        &:nth-of-type(2)
            img
                border-radius: 15px 0 15px 0
    img
        position: static
        width: 100%
        transform: translate(50px, 70px)


@media(max-width:500px)
    .title
        margin-bottom: 18px
    
    .buttons
        flex-direction: column
        .btn
            width: 100%
            height: 50px
    .wrapper
        margin-bottom: 20px
        padding-bottom: 0
    img
        position: static
        width: 100%
        transform: translate(20px, 30px) scale(1.1)
        
</style>