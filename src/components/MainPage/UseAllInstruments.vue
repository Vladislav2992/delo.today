<template>
    <section class="all-instruments">
        <div class="container">
            <h2 class="section__title">Используй все инструменты</h2>
            <div class="wrapper">            
                <div class="instrument">
                    <img src="/finances.png" alt="">

                    <h3 class="title">База знаний</h3>
                    <p class="description">Простое решение для хранения документации, инструкций и онбординга новых сотрудников. В базе знаний можно опубликовать статьи для внутреннего пользования или публиковать информацию для клиентов.</p>
                    <a href="#!" class="link">Узнать подробнее </a>
                </div>

                <div class="instrument">
                    <img src="/finances.png" alt="">

                    <h3 class="title">Гибкая визитная карточка</h3>
                    <p class="description">Соберите свой мобильный сайт на простом конструкторе Аспро.Link и расскажите о себе. Подключите формы для регистрации на свой мастер-класс или принимайте оплату за товары и услуги.</p>
                    <a href="#!" class="link">Узнать подробнее </a>
                </div>
            </div>
        </div>
    </section>
</template>
<style lang="sass" scoped>
.all-instruments
    padding: 80px 0 90px
    background: var(--light-gray)
.wrapper
    display: grid
    grid-template-columns: 1fr 1fr
    gap: 20px

.instrument 
    padding: 40px 30px
    border: 1px solid var(--border)
    border-radius: 15px
    background: #fff
    display: flex
    flex-direction: column
img
    margin: 0 auto 37px auto    

.title
    font-size: clamp(20px, 4vw, 24px)
    font-weight: 500
    font-family: 'Jost', sans-serif
    margin-bottom: 21px

.description 
    margin-bottom: 30px
    color: var(--gray)

.link 
    display: inline-block
    width: fit-content
    padding-right: 50px
    font-weight: 600
    font-size: 15px
    text-decoration: underline
    position: relative
    margin-top: auto
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
        padding-right: 55px

@media(max-width:850px)
    .all-instruments
        padding: 50px 0
    .wrapper
        grid-template-columns: 1fr
        text-align: center
    .link
        margin: auto
        margin-bottom: 0 
    img
        margin: 0 auto 30px 0 
@media(max-width:500px)
    .instrument
        padding: 40px 20px
</style>