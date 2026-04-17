<script setup>
import { ref } from 'vue';

const flg = ref(true);

const num = ref(0);
setInterval(() => {
  num.value++;
}, 200);

</script>

<template>
  <!-- v-if=true 이면  -->
  <!-- v-show 는 자주 보였다가 사라졌다 하는데 사용함 -->
  <!-- v-if 는 한번정도만 on/off 되는 요소에 사용함 -->
  <button type="button" @click="flg = !flg">온/오프</button>
  <h1 v-show="flg">브이쇼</h1>
  <h1 v-if="num % 3 === 0" style="color: red;">조건부 렌더링</h1>
  <h1 v-else-if="num % 2 === 0" style="color: blue;">조건부 렌더링 2</h1>
  <h1 v-else-if="num % 2 === 0" style="color: yellow;">조건부 렌더링 2</h1>
  <h1 v-else>없음</h1>
</template>

<style>

</style>