<template>
    <div class="advantages">
        <div class="advantages__text">
            <span>Softline</span> – ведущий поставщик IT-решений и сервисов.* Мы предлагаем комплексные IT-решения, облака, программное и аппаратное обеспечение, решения по цифровой трансформации и кибербезопасности, а также широкий спектр IT-услуг.
        </div> 
        <div class="advantages__numbers">
            <div class="advantages__numbers-wrapper">
                <div class="advantages__numbers-item">
                    <div class="advantages__numbers-number"><span>></span>30 лет</div>
                    <div class="advantages__numbers-description">на IT-рынке</div>  
                </div>
                <div class="advantages__numbers-item">
                    <div class="advantages__numbers-number">4600</div>
                    <div class="advantages__numbers-description">сотрудников в России</div> 
                </div>
                <div class="advantages__numbers-item">
                    <div class="advantages__numbers-number">25</div>
                    <div class="advantages__numbers-description">городов России</div> 
                </div>
                <div class="advantages__numbers-item">
                    <div class="advantages__numbers-number plus">2000 </div>
                    <div class="advantages__numbers-description">разработчиков</div>
                </div>
                <div class="advantages__numbers-item">
                    <div class="advantages__numbers-number plus">3000</div>
                    <div class="advantages__numbers-description">сотрудников ежегодно <br> проходят оценку и обучение</div>
                </div>

                
                
                 
                 
            </div>
        </div>
    </div>
    
</template>

<script setup>
    
</script>

<style lang="scss" scoped>
.advantages {
    padding: 100px 70px;
    &__text {
        padding: 100px 110px;
        box-shadow: 0px 0px 32px 0px rgba(0, 0, 0, 0.08);
        color: #444;
        font-family: Proxima Nova Condensed;
        font-size: 32px;
        font-style: normal;
        font-weight: 600;
        line-height: 120%;
        text-align: center;
    }
    &__text span {
        color: #B01736
    }
    &__numbers {
        padding: 100px 110px;
        display: flex;
        
    }
    &__numbers-wrapper {
        display: flex;
        gap: 80px 180px;
        flex-wrap: wrap;
        justify-content: center;
    }
    &__numbers-description {
        margin-top: 4px;
    }

    &__numbers-number {
        display: flex;
        gap: 10px;
        color: #A30C33;
        font-family: Proxima Nova Condensed;
        font-size: 80px;
        font-style: normal;
        font-weight: 600;
        line-height: 80%; /* 64px */

        span {
            color: #A30C33;
            font-family: Proxima Nova Condensed;
            font-size: 64px;
            font-style: normal;
            font-weight: 900;
            line-height: 100%; /* 64px */
        }
    }
.plus::after {
    content: '+';
    display: block;
    font-size: 64px;
}
}
</style>

