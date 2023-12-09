<template>
    <div class="benefits">
        <div class="benefits__container">
            <h2 class="benefits__title">Компенсационный пакет</h2>
            <div class="benefits__wrapper">
                <div class="benefits__packet" v-for="(benefit, index) in benefits" :key="index">
                    <img :src="benefit.icon" class="benefits__packet-icon">
                    <div class="benefits__packet-title">{{ benefit.title }}</div>
                </div>
            </div>
            <div class="divider"></div>
            
                <h2 class="benefits__programm-title">Программа дополнительной мотивации <br> <span>доплата 12% от суммы</span></h2>
            <div class="benefits__programm-wrapper">
                <div class="benefits__programm-content" v-for="(programm, index) in programms" :key="index">
                    <img :src="programm.icon" class="benefits__packet-icon">
                    <div class="benefits__packet-title">{{ programm.title }}</div>
                </div>
            </div>  
        </div>
    </div>
       
</template>

<script setup>
import health from '../assets/icons/health.png'
import birthday from '../assets/icons/birthday.png'
import phone from '../assets/icons/phone.png'
import power from '../assets/icons/power.png'
import relationship from '../assets/icons/relationship.png'
import orgTech from '../assets/icons/org.png'
import home from '../assets/icons/home.png'
    const benefits = [
        {icon: health, title: 'ДМС'},
        {icon: birthday, title: 'Выходной в день рождения'},
        {icon: phone, title: 'Корпоративная мобильная связь'},
        {icon: power, title: 'Корпоративные скидки на спорт'},
        {icon: relationship, title: 'LTI'},
    ]

    const programms = [
        {icon: orgTech, title: 'Оргтехники'},
        {icon: health, title: 'ДМС'},
        {icon: home, title: 'Ипотеки'},
    ]
</script>

<style lang="scss" scoped>
.benefits {
    background: #FFF;
    box-shadow: 0px 0px 40px 0px rgba(0, 0, 0, 0.06);
    &__container {
      margin: 100px 70px 0;  
    }
    &__title {
        color: #444;
        text-align: center;
        font-family: Proxima Nova Condensed;
        font-size: 56px;
        font-style: normal;
        font-weight: 600;
        line-height: 100%;
        padding-top: 80px;
    }
    &__wrapper {
        display: flex;
        justify-content: space-around;

        padding: 50px 112px 75px;
        gap: 16px;
    }
    &__packet {
        max-width: 178px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    &__packet-title {
        text-align: center;
        margin-top: 10px;
        color: #444;
        text-align: center;
        font-family: Proxima Nova Condensed;
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 110%; /* 19.8px */
    }
    &__programm-title {
        color: #444;
        text-align: center;
        font-family: Proxima Nova Condensed;
        font-size: 40px;
        font-style: normal;
        font-weight: 600;
        line-height: 120%;
        margin-top: 70px;
    }
    &__programm-title span {
        color: #B01736;
    }
    &__programm-wrapper {
        display: flex;
        padding: 50px 306px 80px;
        justify-content: space-between;
    }
    &__packet-title {
        color: #444;
        text-align: center;
        font-family: Proxima Nova Condensed;
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 110%; /* 19.8px */
    }
.divider {
    margin: 0 30px;
    height: 1px;
    background: #000;
    opacity: 0.1;
}
}
</style>