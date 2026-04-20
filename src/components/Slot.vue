<script setup>
// 슬롯은, 템플릿 컨텐츠를 부모컴포넌트에서 자식컴포넌트로 전달하고,
// 자식컴포넌트에서 렌더링 처리하는것.
// 부모컴포넌트에서, 자식컴포넌트의 내용을 변경하고 싶을때.
import { ref } from 'vue';
import SlotChild from './SlotChild.vue';

const cnt = ref(0);

</script>

<template>
  <h1>슬롯</h1>


  <!-- 보내줄 슬롯은, Slot에서는 출력이 안됨. -->
   <!-- 자식컴포넌트에, <slot> 으로 전달됨 -->
  <SlotChild>
    <div>
      <h2>보내줄 슬롯 : {{ cnt }}</h2>
      <h3>아아아</h3>
    </div>
  </SlotChild>


</template>

<style>

</style>