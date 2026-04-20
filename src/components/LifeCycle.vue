<script setup>
import { onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUnmounted, onUpdated, ref } from 'vue';

const cnt = ref(0);


// 라이프사이클 훅 이다.

// !화면에 출력하기 전에, 어떤 작업을 진행하는 메소드
onBeforeMount(() => {
  console.log('onBeforeMount', cnt.value);
});


// 화면에 출력되고 난 다음, 어떤 작업을 진행하는 메소드
onMounted(() => {
  cnt.value++;
  console.log('onMounted', cnt.value);
});

// !업데이트가 일어났을때 일어나는 함수들

// 업데이트가 일어나기 전에 액션을 취하는 함수(화면의 리렌더링(새로고침)이 일어나기 전)
onBeforeUpdate(() => {
  console.log('onBeforeUpdate')
});

// 업데이트가 일어나고 액션을 취하는 함수 (화면의 리렌더링 ( 새로고침) 이 일어난 후)
onUpdated(() => {
  console.log('onUpdated')
})


// !언마운트가 일어났을때 발생하는 함수들

onBeforeUnmount(() => {
  console.log('onBeforeUnmount')
})

onUnmounted(() => {
  console.log('onUnmounted')
})

</script>

<template>
  <h1>라이프 사이클: {{ cnt }}</h1>
  <button type="button" @click="cnt++">증가</button>
</template>

<style>

</style>