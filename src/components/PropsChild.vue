<script setup>
// 자식 컴포넌트에서는 defineProps() 를 이용해 넘어온 데이터 선언
// 이떄, 부모컴포넌트에서 넘겨줄 때 사용한 키를 사용해 선언
// 데이터 타입도 지정함



// {} 해서 객체를 정의해주면 됨. (객체정의 방식)
// 객체정의방식은, '키' : 내가 전달받을 값의 데이터타입(타입의 첫글자는 대문자로)
// 배열로도 줄수 있는데 , 아래처럼 줄수 있다.
defineProps(['cnt','page']);
 

//  타입스크립트에서는 이렇게 써야한다고함.
//  const props = defineProps({
//   'cnt' : Number,
//   'page' : Number,
//  })
  
// 자식 컴포넌트에서는 defineEmits() 를 이용해 넘어온 컴포넌트 이벤트 선언
//  이때 부모 컴포넌트에서 넘겨줄 때 사용한 이벤트 명을 사용해 선언
// 아래는 명시적 선언방식. 사용하려면, 변수명만 적어주면 됨 (명시적 선언이 더 안정적)
const emit =  defineEmits(['minusCnt']);
</script>

<template>
  <h1>{{page}}프롭스 자식 컴포넌트 {{ cnt }}</h1>
  <!-- @emit('부모에서 보내어진 함수명') -->
  <button type="button" @click="emit('minusCnt', 10)">감소(자식쪽)</button>
</template>

<style scoped>

</style>