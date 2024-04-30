<template>
    <aside class="appointment">
        <div class="container">
            <div class="left">
                <!-- <h2 class="logo">delo.today</h2> -->
                <div class="inner">
                    <h3>Запишись на онлайн демонстрацию</h3>
                    <p>Расскажем о тонкостях системы и ответим на вопросы на 30-минутном бесплатном уроке.</p>
                    <div class="input-wrapper">
                        <input type="text" class="input" placeholder="Ваша почта или номер телефона">
                        <button class="btn btn_transparent">Записаться</button>
                    </div>
                </div>
            </div>

            <div class="right">
                <img src="/aside-img.png" alt="">
            </div>

            <svg class="decor-1" width="692" height="295" viewBox="0 0 692 295" fill="none" xmlns="http://www.w3.org/2000/svg">
            <ellipse cx="281" cy="231" rx="411" ry="231" fill="url(#paint0_radial_7418_1734)" />
            <defs>
                <radialGradient id="paint0_radial_7418_1734" cx="0" cy="0" r="1" gradientUnits="userSpaceOnUse" gradientTransform="translate(281 231) rotate(90) scale(231 411)">
                <stop offset="0.209" stop-color="#4D5AD1" />
                <stop offset="0.689" stop-color="#4D5AD1" stop-opacity="0.5" />
                <stop offset="1" stop-color="#4D5AD1" stop-opacity="0" />
                </radialGradient>
            </defs>
            </svg>

            <svg class="decor-2" width="557" height="602" viewBox="0 0 204 300" fill="none" xmlns="http://www.w3.org/2000/svg">
            <ellipse cx="278.5" cy="131" rx="278.5" ry="301" fill="url(#paint0_radial_7418_1735)" />
            <defs>
                <radialGradient id="paint0_radial_7418_1735" cx="0" cy="0" r="1" gradientUnits="userSpaceOnUse" gradientTransform="translate(278.5 131) rotate(90) scale(301 278.5)">
                <stop offset="0.209" stop-color="#4D5AD1" />
                <stop offset="0.689" stop-color="#4D5AD1" stop-opacity="0.5" />
                <stop offset="1" stop-color="#4D5AD1" stop-opacity="0" />
                </radialGradient>
            </defs>
            </svg>
        </div>
    </aside>
</template>

<style lang="sass" scoped>
   
.container
    overflow: hidden   
    color: #fff
    max-width: 1240px
    display: flex
    justify-content: space-between
    align-items: center
    gap: 5px
    border-radius: 15px
    background: var(--dark-blue)
    padding: 25px 50px 
    position: relative

.decor-1 
    position: absolute
    left: 0
    bottom: -10%
    z-index: 1
.decor-2 
    position: absolute
    right: -20%
    bottom: 0
    z-index: 1

.logo
    font-family: 'Josefin Sans', sans-serif
    font-size: 28px
    font-weight: 600
    line-height: 130%
    margin-bottom: 10px
    position: relative
    z-index: 2
.inner 
    // border: 1px solid rgba(234, 235, 236, .2)
    // border-radius: 15px
    // padding: 20px 15px
    display: flex
    flex-direction: column
    gap: 20px
    // backdrop-filter: blur(33px)
    // box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.15)
    // background: rgba(255, 255, 255, 0.2)
    position: relative
    z-index: 2
    width: 79%

h3
    font-family: 'Jost', sans-serif
    font-weight: 500
    font-size: clamp(20px, 4vw, 24px)
    line-height: 130%

.input-wrapper
    position: relative    
    overflow: hidden
.input
    border: 1px solid rgba(102, 110, 170, 0.3)
    padding: 15px 200px 15px 20px
    width: 100%
    height: 100%
    font-family: 'Roboto', sans-serif
    font-size: 14px
    border-radius: 40px

    &::placeholder
        font-family: 'Roboto', sans-serif
        font-size: 14px
.btn
    position: absolute
    right: 4px
    top: 50%
    transform: translateY(-50%)
    background: #fff
    border-color: var(--black)
    color: var(--black)
    width: 190px

    &:hover 
        background: #3A3A3A
        color: #fff

.right
    position: relative
    z-index: 2

@media(max-width:950px)
    .container
        flex-direction: column
        padding: 30px 20px
        margin: 0 15px
    .inner
        width: 100%
@media(max-width:550px)
    .btn
        position: static
        transform: translate(0)
        width: 100%
        height: 50px
        background: #000
        color: #fff
    .inner
        gap: 15px
        margin-bottom: 52px
    .input-wrapper
        display: flex
        flex-direction: column
        gap: 10px
    .input
        height: fit-content
        padding: 13px 30px
        height: 50px
</style>