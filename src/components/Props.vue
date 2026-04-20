<script setup>
// 프록스 : 부모컴포넌트에서, 자식컴포넌트로 데이터를 전달하는 사용자 정의 속성
// 기본 읽기전용. 단방향 데이터바인딩
import { ref } from 'vue';
import PropsChild from './PropsChild.vue';


const cnt = ref(0);


//컴포넌트 이벤트 :
// `$emit` 메소드를 사용해서, 부모컴포넌트와 자식컴포넌트 간에
//  이벤트를 수신 or 발신
// - 부모 컴포넌트 에서는 `v-on` 을 사용하여 수신
// 방법 : - `@이벤트명 = "실행할 js 코드"` 자식컴포넌트 태그 속성으로 추가
// - 자식 컴포넌트 에서는 `$emit('이벤트명')` 으로 발신
// 아규먼트가 복수 일 경우 가변 파라미터로 작성. `$emit('이벤트명'[, ...아규먼트])`
function minusCnt(num){
  cnt.value -= num;
}
</script>

<template>
  <h1>프롭스1 {{ cnt }}</h1>
  <button type="button" @click="cnt++">증가(부모쪽)</button>

  <!-- 자식 컴포넌트에 ` :키명="값"`  -->
  <!-- 전달해줄 이름 = "전달해줄 값" 보통은 같은이름으로 전달 -->

  <PropsChild :cnt="cnt" :page="1" @minusCnt="minusCnt"/> 
</template>

<style scoped>

</style>