<template>
    <section class="about-crm">
        <div class="container">
            <div class="content">
                <h3 class="title">Программа CRM для малого бизнеса</h3>
                <p class="description">Управлять рабочими процессами нужно не только крупным компаниям. Малый бизнес тоже может использовать онлайн-CRM, чтобы сделать свою жизнь простой. Автоматизация продаж разгрузит менеджеров, а эффективное взаимодействие по задачам сделает из сотрудников команду. Контролируйте каждый этап проекта и поддерживайте контакт с заказчиком, чтобы показать персональный подход к клиенту.</p>
                <a href="#!" class="link">Узнать подробнее </a>
            </div>
            <div class="img">
                <img src="/img-4.png" alt="">
            </div>
        </div>
    </section>
</template>
<style lang="sass" scoped>
.container
    display: grid
    grid-template-columns: 1fr 1fr
    align-items: center

.img
    margin-left: auto

.content 
    display: flex
    flex-direction: column
    gap: 30px

.title
    font-size: clamp(20px, 4vw, 24px)
    font-weight: 500
    font-family: 'Jost', sans-serif
.description
    color: var(--gray)
.link 
    display: inline-block
    width: fit-content
    padding-right: 35px
    font-weight: 600
    font-size: 15px
    text-decoration: underline
    position: relative
    transition: padding .3s

    &::after
        content: ""
        position: absolute
        width: 25px
        height: 12px
        right: 0
        top: 50%
        transform: translateY(-50%)
        background: url('../../assets/img/arrow-right.svg') no-repeat
    
    &:hover
        padding-right: 40px
@media(max-width:950px)
    .container
        grid-template-columns: 1fr
    .img
        margin: 0
        margin-top: 30px
</style>