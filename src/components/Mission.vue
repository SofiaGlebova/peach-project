<template>
    <div class="mission">
        <img src="../assets/img/mission_bg.png" alt="mission_bg" class="mission__bg">
        <div class="mission__content">
           <h2 class="mission__content-header">Миссия Softline</h2> 
           <div class="mission__content-description">Мы помогаем организациям трансформироваться, работать эффективно и безопасно в условиях цифровой экономики.</div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.mission {
    display:inline-block;   
    position:relative;
    &__content {
        position: absolute; 
        bottom: 140px;
        padding-left: 68px;
        padding-right: 72px;
    }
    &__content-header {
        color: #FFF;
        text-align: center;
        font-family: Proxima Nova Condensed;
        font-size: 56px;
        font-style: normal;
        font-weight: 600;
        line-height: 100%;
        margin-bottom: 40px;
    }
    &__content-description {
        color: #FFF;
        text-align: center;
        font-family: Proxima Nova Condensed;
        font-size: 32px;
        font-style: normal;
        font-weight: 400;
        line-height: 150%; /* 48px */
    }
}
</style>