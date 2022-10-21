<template>
    <div class="content">
        <h1 class="title">{{ name }}</h1>
        <div class="display happiness">
            <h2>Happiness</h2>
            <div>
                <img class="icon" src="../../assets/icon/icons8-content-100.png" alt="">
                <h2>{{ happiness }} %</h2>
            </div>
        </div>
        <div class="display income">
            <h2>Income</h2>
            <div>
                <img class="icon" src="../../assets/icon/icons8-argent-100.png" alt="">
                <h2>{{ income }} $</h2>
            </div>
        </div>
        <div class="display price buy" v-if="isBuy">
            <h2>Buy</h2>
            <h2>{{ price }} $</h2>
        </div>
        <div class="display price sell" v-if="!isBuy">
            <h2>Sell</h2>
            <h2>{{ price }} $</h2>
        </div>
    </div>
</template>

<script setup>
defineProps({
    name: String,
    happiness: {
        type: [String, Number],
        default: '?'
    },
    income: {
        type: [String, Number],
        default: '?'
    },
    price: {
        type: [String, Number],
        default: '?'
    },
    isBuy: {
        type: Boolean,
        default: true
    }
})
</script>

<style scoped>
.content{
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    color: #232323;
}
.content>.display>h2{
    font-size: 24px;
    font-weight: 500;
}
.content>.display>div>h2{
    font-size: 20px;
    font-weight: 400;
}
.title{
    font-weight: bold;
    font-size: 32px;
}
.icon{
    width: 32px;
    height: 32px;
}
.display{
    width: 200px;
    height: 80px;
    margin: 10px 0px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #F8F5F2;
    border-radius: 5px;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
.display>div{
    display: flex;
    width: 100%;
    justify-content: center;
    flex-direction: row;
    align-items: center;
    gap: 15px;
}
.price{
    color: #F8F5F2;
    cursor: pointer;
}
.price>h2{
    font-weight: 600 !important;
}

.buy{
    background-color: #078080;
}
.sell{
    background-color: #f45d48;
}


</style>