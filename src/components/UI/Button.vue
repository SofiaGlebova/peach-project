<template>
    <button class="button">
        <slot />
    </button>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.button {
    padding: 18px 28px;
    border: none;
    border-radius: 8px;
    background: #B01736;
    color: #FFF;
    font-family: Proxima Nova Condensed;
    font-size: 18px;
    font-style: normal;
    font-weight: 600;
    line-height: 20px; /* 111.111% */
    cursor: pointer;
}
.button:hover {
    background: #D43152;
}
</style>