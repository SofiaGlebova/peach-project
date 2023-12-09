<template>
    <div class="direction">
        <h2 class="direction__title">Направления бизнеса</h2>
        <div class="direction-wrapper">
            <div class="direction__items">
                <div class="direction__item" :style="{ height: '260px' }" v-for="(direction, index) in directions" :key="index">
                    <img :src="direction.img" alt="direction">
                    <div class="effect">
                        <div class="direction__item-title">{{ direction.title }}</div>
                        <div class="direction__item-description">{{ direction.descr }}</div>  
                    </div>
                    
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import cyber from '../assets/img/cyber.jpg'
import cloud from '../assets/img/cloud.jpg'
import man from '../assets/img/man.jpg'
import support from '../assets/img/support.jpg'
import im from '../assets/img/impor.jpg'

    const directions = [
        {img: support, title:'Решения Softline', descr: 'ГК Softline предлагает клиентам собственную линейку оборудования (ПК, серверы, торговое оборудование и проч.), разработку программных продуктов, облачных решений, решений в области информационной безопасности.'},
        {img: cyber, title:'Кибербезопасность', descr: 'Softline обладает всеми необходимыми государственными лицензиями для организации проектов по информационной безопасности и аттестации. '},
        {img: im, title:'Импортозамещение', descr: 'ГК Softline обладает широчайшим портфелем решений и услуг для импортозамещения, включая ПО и оборудование собственного производства.'},
        {img: cloud, title:'Облачные решения', descr: 'Softline использует современные облачные решения как российских, так и международных вендоров для масштабирования бизнеса своих клиентов. Подписки, услуги, трансформация.'},
        {img: man, title:'Цифровая трансформация и разработка ПO', descr: 'Softline использует современные технологи и новые возможности для увеличения производительности бизнеса заказчика. В штате ГК Softline - 2000+ разработчиков, которые трансформируют ПО под нужды конкретного предприятия.'},
        {img: support, title:'Техническая поддержка Softline', descr: '200+ инженеров, 24 часа в сутки, 7 дней в неделю, 12 месяцев в году, сервисное партнерство с 30+ мировыми производителями.'}
    ]
</script>

<style lang="scss" scoped>
.direction {
    &__title {
        color: #444;
        text-align: center;
        font-family: Proxima Nova Condensed;
        font-size: 56px;
        font-style: normal;
        font-weight: 600;
        line-height: 100%; /* 56px */
        margin-top: 100px;
    }
    &__items {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 22px 20px;
        margin: 55px auto 0;
        width: 100%;
        padding: 0;

    }
    &__item {
        width: 100%;
        position: relative;
        display: inline-block;
        margin: 0;
        overflow: hidden; 
    }
    &__item-title {
        color: white;
        font-family: Proxima Nova Condensed;
        font-size: 24px;
        position: absolute;
        font-style: normal;
        font-weight: 600;
        line-height: 100%;
        padding: 28px 20px;

    }
    &__item-description {
        max-width: 480px;
        margin-top: 75px;
        margin-left: 20px;
        color: var(--1, #FFF);
        font-family: Proxima Nova Condensed;
        font-size: 17px;
        font-style: normal;
        font-weight: 400;
        line-height: 140%;
        
    }
.effect {
    // opacity: 0.6;
    background: rgba($color: #2D3653, $alpha: 0.6);
    position: absolute;
    top: 180px;
    left: 0;
    width: 100%;
    height: 100%;
    transition: all 0.4s ease-in-out;
}
.effect:hover {
    position: absolute;
    overflow: hidden;
    top: 0;
    left: 0;
}
}
</style>