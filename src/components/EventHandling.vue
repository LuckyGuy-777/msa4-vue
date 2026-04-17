<script setup> //setup 키워드가 있어야함.
import { ref } from 'vue';

const cnt = ref(0);


function resetCnt(num){
  cnt.value = num;
}
</script>

<template>
  <h1>이벤트 핸들링 {{ cnt }}</h1>
  <button type="button" @mouseenter="cnt++">인라인 핸들러</button>
  <button type="button" @click="resetCnt(9)">메소드 핸들러</button>
  <!-- keydown.up은 ,마우스올렸을때, 1추가 -->
  <input type="number" @keydown.up ="cnt++" v-model = "cnt">
</template>

<style>

</style>