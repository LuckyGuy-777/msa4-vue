<script setup>
  // 자바스크립트 코드치는 부분
  import DataBinding from './components/DataBinding.vue';
  import EventHandling from './components/EventHandling.vue';
  import ConditionalRenderling from './components/ConditionalRenderling.vue';
  import ListRanderling from './components/ListRanderling.vue';
  import Watchers from './components/Watchers.vue';
</script>

<template>
  <!-- html 작성 부분 -->
   <!-- v-if 는 조건부 렌더링. false를 줬으니, 요소 표시안됨 -->
   <DataBinding v-if="false"/>
   <EventHandling v-if="false"/>
   <ConditionalRenderling v-if="false"/>
   <ListRanderling v-if="false" />
   <Watchers />
</template>

<style>

 /* css 작성 부분 */
</style>