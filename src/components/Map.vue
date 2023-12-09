<template>
    <div class="map">
        <div class="container">
            <div class="map-nav">
                <h2 class="map-nav__main-title">Офисы Softline</h2>
                <button @click="toggleDropdown" :class="['map-nav__main-icon', {['rotate']: isActive}]">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
                        <path d="M2.10156 7.99683L12.1016 16.0179L22.1016 7.99683" stroke="#444444" stroke-width="3"/>
                    </svg>
                </button>

                <div :class="[
                    'dropdown', 
                    { ['active']: isActive }
                ]" >
                    <div class="dropdown__container">
                        <template 
                            v-for="(value, name, index) in regions" 
                            :key="index"
                        >
                            <div
                                v-if="!['Все'].includes(name)"
                                class="regions" 
                            >
                                <div class="region">
                                {{ name }}
                                <div class="region__cities" 
                                v-if="name !== 'Москва'">
                                    <div 
                                        
                                        v-for="city in value"
                                        :key="city.name"
                                    >
                                        {{ city.name }}
                                    </div>
                                </div>
                                </div>
                            </div>
                        </template>
                    </div>
                </div>
            </div>
            <div :class="['map__tabs', {'white': isActive}]" >
                <button  
                    class="map__tabs-menu" 
                    v-for="(value, name, index) in regions" 
                    :key="index"
                >
                    <div @click="() => onSelectRegion(name)" :class="['map-tab', {['activeRegion']: selectedRegion === name}]">{{ name }}</div>
                </button>
            </div>  
        </div>
        <div class="map__position-city">
            <img 
                class='map-map'
                src="../assets/img/map.png" alt="">
            <template 
                v-for="(value, name, index) in regions"                
                :key="index"
            >
                <template v-if="selectedRegion === 'Все' || selectedRegion === name">
                    <div
                        v-for="city in value"
                        :key="city.name"
                        class="coordinates" 
                        :style="{top:`${city.position.y}px`, left:`${city.position.x}px`}"
                    >
                    {{city.name}}
                </div>
                </template>
            </template>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
    const getCityObject = (name, x, y) => {
        return {
            name,
            position: {
                x,
                y
            }
        }
    }

    const selectedRegion = ref('Все')

    const toggleDropdown = () => {
        isActive.value = !isActive.value
    }
    
    const onSelectRegion = (value) => {
        selectedRegion.value = value
    }

    const regions = {
        'Все': [],
        'Москва': [
            getCityObject('Москва', 151, 234)
        ],
        'Центр': [
            getCityObject('Воронеж', 98, 255),
            getCityObject('Ярославль', 177, 207),
            getCityObject('Белгород', 93, 285),
        ],
        'Северо-Запад': [
            getCityObject('Санкт-Петербург', 134, 147),
            getCityObject('Калининград', 42, 134)
        ],
        'Юг': [
            getCityObject('Ростов-на-Дону', 66, 327),
            getCityObject('Краснодар', 53.3, 385),
            getCityObject('Волгоград', 111, 368)
            
        ],
        'Волга': [
            getCityObject('Казань', 260, 307),
            getCityObject('Самара', 200, 313),
            getCityObject('Уфа', 270, 343),
            getCityObject('Оренбург', 226, 371),
            getCityObject('Н. Новгород', 192, 269)
        ],
        'Урал': [
            getCityObject('Екатеринбург', 315, 335),
            getCityObject('Челябинск', 317, 370),
            getCityObject('Пермь', 387, 308),
            getCityObject('Сургут', 442, 320),
            getCityObject('Тюмень', 415, 370),
            getCityObject('Ижевск', 334, 299),
        ],
        'Сибирь': [
            getCityObject('Новосибирск', 513, 463),
            getCityObject('Омск', 478, 484),
            getCityObject('Томск', 593, 441),
            getCityObject('Красноярск', 638, 464),
            getCityObject('Иркутск', 697, 497)
        ],
        'Дальний Восток': [
            getCityObject('Хабаровск', 985, 478),
            getCityObject('Владивосток', 966, 581)
        ]
    }

    let isActive = ref(false)
</script>

<style lang="scss" scoped>
.container {
    display: flex;
    position: relative;
    box-shadow: 0px 0px 40px 0px rgba(0, 0, 0, 0.06);
}
.map-nav {
    display: flex;
    gap: 0 16px;
    padding: 28px 0 28px 70px;
    &__main-title {
        color: #444;
        font-family: Proxima Nova Condensed;
        font-size: 24px;
        font-style: normal;
        font-weight: 600;
        line-height: 100%;
    }
    &__main-icon {
        border: none;
        background-color: white;
        cursor: pointer;
        transition: all 0.4s ease-in-out;
    }
}
.map__tabs-menu {
    border: none;
    background: white;
    cursor: pointer;
}
.map__tabs {
    padding: 30px 70px 0;
    display: flex;
    gap: 30px;
    align-items: flex-start;
}
.map-tab {
    color: #444;
    font-family: Proxima Nova Condensed;
    font-size: 18px;
    font-style: normal;
    font-weight: 600;
    line-height: 20px;
    height: 54px;
}
.map-map {
    display: block;
    margin: 90px auto 100px;
    // position: relative;
}
.region {
    display: flex;
    flex-direction: column;
    gap: 10px;
    font-weight: 600;
    &__cities {
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
}

.coordinates {
    position: absolute;
    color: #444;
    text-align: right;
    font-family: Proxima Nova Condensed;
    font-size: 14px;
    font-style: normal;
    font-weight: 600;
    line-height: 100%; /* 14px */
}
.coordinates::after {
    content: '';
    display: block;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #444;
    position: absolute;
    top: -75%;
    left: 43%;
}
.dropdown {
    position: absolute;
    background-color: white;
    padding: 30px 60px;
    width: 100%;
    top: 70px;
    left: 0; 
    opacity: 0;
    box-shadow: 0px 0px 32px 0px rgba(0, 0, 0, 0.06);
    transition: all 0.4s ease-out;
    z-index: 1;
    
    &__container {
        display: flex;
        gap: 24px;
        justify-content: center;
    }
}
.map__position-city {
    position: relative;
}
.active {
    opacity: 1;
    top: 100px;
}
.activeRegion {
    color: #A30C33;
    border-bottom: 3px solid #A30C33;
}
.rotate {
    transform: scale(1, -1);
    transition: all 0.3s ease-out;
}
.white {
    opacity: 0.2;
}

</style>