<script setup>
import { ref, watch } from 'vue';



// 반응형 속성이 변경될때마다 감지하고, 특정로직을 실행
const email = ref('');
const flgEmail = ref(true);
const flgIsExecuted = ref(false);

// 첫번째 콜백 : 감시할 대상 (ref, reactive), 두번째 콜백 : 이메일
// 세번쨰 : 옵션
// 유저입력값 체크, 상태값 체크 등을 할때 watch() 사용함
watch(email, () => {
  if(email.value.includes('@')){
    flgEmail.value=true;
  }else {
    flgEmail.value=false;
  }
  flgIsExecuted.value = true;
})


const pw = ref('');
const pwClass = ref('');

watch(pw, () => {
  if(pw.value.includes('@')){
    pwClass.value = 'outline-green'
  }else{
    pwClass.value = 'outline-red'
  }
});

</script>

<template>
  <h1>감시자</h1>
  <div v-if="flgIsExecuted">
    <span v-if="flgEmail">O</span>
    <span v-else>X</span>
  </div>
  <input type="text" v-model="email">
  <input type="text" v-model="pw" :class="pwClass">
</template>

<style>
input {
  outline: none;
}
.outline-green {
  border: 2px solid rgb(104, 221, 104);
}
.outline-red {
  border: 2px solid rgb(187, 24, 24);
}
</style>