<script setup>
defineProps({
    title: String,
    oldPrice: Number,
    newPrice: Number,
    isBestChoise: Boolean
})
</script>

<template>
    <div :class="['tariff', {'best-choise' : isBestChoise}]">        
            <h3 class="title">{{ title }}</h3>
            <p class="description">Задачи и проекты для работы распределенных команд и взаимодействия отделов</p>
        <div class="prices">
            <div class="new">
                {{ newPrice }} руб.
                <span class="time">За год</span>
            </div>
            <div class="old">
                <div>
                    <p><span class="line-through">{{ oldPrice }}</span> руб.</p>
                </div>
                <span class="time">За месяц</span>
            </div>
        </div>
        
        <button class="btn">Начать бесплатно</button>
        
        <ul>
            <li>Календарь</li>
            <li>Управление сотрудниками</li>
            <li>15 Сотрудников</li>
            <li>Отчеты и аналитика</li>
            <li>Чаты</li>
            <li>Задачи и проекты</li>
        </ul>
    </div>
</template>
<style lang="sass" scoped>
.tariff
    padding: 30px 20px
    border: 1px solid var(--border)
    border-radius: 8px
    box-shadow: 0 4px 20px 0 rgba(0, 0, 0, 0.05)
    background: #fff
    display: flex
    flex-direction: column
    position: relative

    &.best-choise
        border-color: #9C88FF

        &::before
            content: 'Лучший выбор'
            position: absolute
            top: -15px
            right: 17px
            color: #fff
            padding: 8px 14px
            border-radius: 5px
            font-family: 'Jost', sans-serif
            font-size: 12px
            font-weight: 500
            line-height: 120%
            display: inline-block
            background: var(--dark-blue)

.title
    font-size: clamp(20px, 4vw, 24px)
    font-weight: 500
    line-height: 105%
    font-family: 'Jost', sans-serif
    margin-bottom: 8px
.description 
    margin-top: auto
    margin-bottom: 30px
    color: var(--gray)
.prices 
    display: flex
    gap:15px
    margin-bottom: 22px
.new
    display: flex
    flex-direction: column
    font-size: 24px
    font-weight: 500
    font-family: 'Jost', sans-serif
    
.old
    display: flex
    flex-direction: column
    p
        font-size: 16px
        font-weight: 500
        font-family: 'Jost', sans-serif
        

.line-through
    text-decoration: line-through
    line-height: 105%
.time
    font-family: 'Roboto'
    font-size: 12px
    color: var(--gray)
.btn
    width: 100%
    margin-bottom: 27px
    font-size: 14px

ul
    display: flex
    flex-direction: column
    gap: 9px
li
    position: relative
    padding-left: 20px
    color: var(--gray)

    &::before 
        content: ''
        position: absolute
        top: 50%
        transform: translateY(-50%)
        left: 0
        width: 13px
        height: 9px
        background: url('../../assets/img/checked.svg') no-repeat
</style>