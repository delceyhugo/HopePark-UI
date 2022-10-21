<template>
    <div v-if="false" class="card">
        <ul id="sections">
            <li class="section" :class="{ active: sectionNum == 0}" @click="sectionNum = 0">
              <img class="head-icon" src="../../assets/icon/icons8-immobilier-100.png" alt="">
            </li>
            <li class="section" :class="{ active: sectionNum== 1}" @click="sectionNum = 1">
              <img class="head-icon" src="../../assets/icon/icons8-vente-immobilière-100.png" alt="">
            </li>
            <li class="section" :class="{ active: sectionNum == 2}" @click="sectionNum = 2">
              <img class="head-icon" src="../../assets/icon/icons8-paramètres-100.png" alt="">
            </li>
        </ul>
        <main>
            <div class="close">
                <img class="head-icon" src="../../assets/icon/icons8-fermer-la-fenêtre-100.png" alt="">
            </div>
            <div class="content">
              <Home v-if="sectionNum === 0"/>
              <Special v-if="sectionNum == 1" />
              <Option v-if="sectionNum == 2" />
            </div>
        </main>
    </div>
    <div v-if="true" class="card">
        <ul id="sections">
            <li class="section active">
              <img class="head-icon" src="../../assets/icon/icons8-immobilier-100.png" alt="">
            </li>
            <li class="section blur">
              <img class="head-icon" src="../../assets/icon/icons8-vente-immobilière-100.png" alt="">
            </li>
            <li class="section blur">
              <img class="head-icon" src="../../assets/icon/icons8-paramètres-100.png" alt="">
            </li>
        </ul>
        <main>
            <div class="close">
                <img class="head-icon" src="../../assets/icon/icons8-fermer-la-fenêtre-100.png" alt="">
            </div>
            <div class="content">
              <Home v-if="sectionNum === 0" :name="props.test.name" :happiness="props.test.happiness" :income="props.test.income" :price="props.test.price" :isBuy="true" />
              <Special v-if="sectionNum == 1" />
              <Option v-if="sectionNum == 2" />
            </div>
        </main>
    </div>

    <!-- :name="name" :happiness="happiness" :income="income" :price="price" :isBuy="true" -->


  
</template>

<script setup>
import { ref } from 'vue'
import { onMounted } from 'vue'
import Home from './Main.vue'
import Special from './Special.vue'
import Option from './Option.vue'
const sectionNum = ref(0)



const props = defineProps({
  test: Object
})




</script>

<style>
#sections{
  display: flex;
  flex-direction: row;
}
.close{
  position: absolute;
  z-index: 1;
  right: 0px;
  top: 0px;
}
.head-icon{
  width: 52px;
  height: 52px;
  cursor: pointer;
}
.section{
  display: grid;
  place-items: center;
  width: 90px;
  height: 65px;
  list-style: none;
  background-color: #222525;
  border-radius: 5px 5px 0px 0px;
  margin-right: 8px;
  cursor: pointer;
}
.active{
  background-color: #FFFFFE;
}
.content{
  width: 350px;
  height: 400px;
  border-radius: 0px 5px 5px 5px;
  background-color: #FFFFFE;
}
.blur{
  opacity: 0.5;
}
</style>