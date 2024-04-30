<template>
    <section class="blog">
        <div class="container">
            <div class="header">
                <h2 class="title">Блог <span>delo.today</span></h2>
                <button class="see-all">Все статьи</button>
            </div>
            <div class="blog__items">
                <div class="blog__item">
                    <img src="/image-1.jpg" alt="">
                    <div class="inner">
                        <h3 class="article__title"><a href="#!">Автоматизация процесса продаж. Как с помощью автодействий ускорить обработку сделок?</a></h3>
                            <p class="date">18 мая 2022</p>
                    </div>
                </div>

                <div class="blog__item">
                    <img src="/image-1.jpg" alt="">
                    <div class="inner">
                        <h3 class="article__title"><a href="#!">Автоматизация процесса продаж. Как с помощью автодействий ускорить обработку сделок?</a></h3>
                            <p class="date">18 мая 2022</p>
                    </div>
                </div>

                <div class="blog__item">
                    <img src="/image-1.jpg" alt="">
                    <div class="inner">
                        <h3 class="article__title"><a href="#!">Автоматизация процесса продаж. Как с помощью автодействий ускорить обработку сделок?</a></h3>
                        <p class="date">18 мая 2022</p>
                    </div>
                </div>
            </div>
        </div>

    </section>
</template>
<style lang="sass" scoped>
.header
    display: flex
    justify-content: space-between
    align-items: center
    margin-bottom: 50px

.see-all
    font-weight: 500
    font-size: 16px
    line-height: 105%
    text-align: right
    color: #9c88ff
    font-family: 'Jost', sans-serif
    padding: 0
    background: transparent
    border: none

.title
    font-weight: 500
    font-size: clamp(24px, 4vw, 36px)
    line-height: 105%
    font-family: 'Jost', sans-serif

    span
        font-family: 'Josefin Sans', sans-serif

.blog__items
    display: grid
    grid-template-columns: 1fr 1fr 1fr
    gap: 20px

.blog__item 
    border-radius: 15px
    overflow: hidden
    box-shadow: 0 4px 20px 0 rgba(0, 0, 0, 0.05)
    background: #fff
.inner
    padding: 19px 20px 20px

.article__title 
    font-weight: 500
    font-size: clamp(16px, 4vw, 18px)
    line-height: 105%
    font-family: 'Jost', sans-serif
    display: flex
    flex-direction: column
    margin-bottom: 20px

.date
    font-size: 13px
    color: #AEB4BF
    margin-top: auto
@media(max-width:750px) 
    .blog__items
        grid-template-columns: 1fr
    img
        width: 100%
</style>