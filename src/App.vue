<script setup>
import Properties from './components/properties/Properties.vue'
import { ref, onMounted} from 'vue'


const store = ref({
  name: '1138 Grant St',
  happiness: 35,
  income: 341,
  price: '146.400',
  isFree: false
})



let hydrateData = (data)=>{
  store.value.name = data.name,
  store.value.happiness = data.happiness,
  store.value.income = data.income,
  store.value.price = data.price,
  store.value.isFree = data.isFree
}
let test1 = () =>{
  console.log('test');
}





</script>

<template>
  <header>
    <div class="wrapper">
      <Properties :test='store'/>
    </div>
  </header>
</template>

<!-- :test="{name: '1138 Grant St',happiness: 35,income: 341,price: 146.400,isFree: false}" -->

<style scoped>

</style>
