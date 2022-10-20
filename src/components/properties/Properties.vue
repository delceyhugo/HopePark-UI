<template>

    <div class="card">
        <ul id="sections">
            <li class="section"></li>
            <li class="section"></li>
            <li class="section"></li>
        </ul>
        <main>
            <div class="close">
                
            </div>
            <div class="content">
              <Home />
            </div>
        </main>
    </div>




  
</template>

<script setup>
import Home from './Main.vue'
import Special from './Special.vue'
import Option from './Option.vue'
defineProps({
  cost: {
    type: String,
    required: true
  }
})
</script>

<style>
#sections{
  display: flex;
  flex-direction: row;
}
.section{
  list-style: none;

}
.content{
  background-color: #FFFFFE;
}
</style>