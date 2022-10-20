<template>
    <div class="content">
        <h1>{{ name }}</h1>
        <div class="display happiness">
            <h2>Happiness</h2>
            <img src="" alt="">
            <h2>{{ happiness }}</h2>
        </div>
        <div class="display income">
            <h2>Income</h2>
            <img src="" alt="">
            <h2>{{ income }}</h2>
        </div>
        <div class="display sell-price">
            <h2>Sell</h2>
            <img src="" alt="">
            <h2>{{ sellPrice }}</h2>
        </div>
    </div>
</template>

<script setup>
defineProps({
    name: String,
    happiness: Number,
    income: Number,
    sellPrice: Number
})
</script>

<style>
.content{
    display: flex;
    flex-direction: column;
}
.name{
    grid-area: title;
}
.display{
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto;
    grid-template-areas:
    "title title";
    background-color: #F8F5F2;
    border-radius: 5px;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
</style>