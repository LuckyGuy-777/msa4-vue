<script setup>
import { reactive, ref } from 'vue'; // vue 가 node_modules을 가르킴
  // 자바스크립트 코드치는 부분

  // ref() 는 vue에 있는 기능. 함수임. 파라미터로 초기값
  // ref() 는 상태를 유지하기위한 변수를 만들고 싶을때 씀.
  // 객체 라고함. 타입제한 x, 되도록 Primitive type에 반응적 참조를 위해 사용
  //  Primitive type에, 좀 더 나은성능을 제공한다.
  const cnt = ref(0);
  // ref객체의 경우 js에서 접근 시, 해당값은 ref.value 프로퍼티로 접근함.
  console.log(cnt.value)


  function add(){
    cnt.value++;
  }

  // reactive는, 객체만 사용가능
  // 해당 객체의 반응적 참조를 위해 사용함
  const info = reactive({
    name : "hong",
    age : 20
  });
  console.log(info.name);


const color = ref('red');

function btnToggle(){
  if(color.value === 'red'){
    color.value = 'blue';
  }else{
    color.value = 'red'
  }
}


const id = ref('')
</script>

<template>
  <!-- html 작성 부분 -->
   <!-- {{ 변수 }} . {{  }} 는, vue 문법임.-->
   <!-- @click=" " 에는, 쌍따옴표 안에는, 콜백함수나, 자바스크립트 코드를 넣어줌 -->
    <!--  @click=" " 은, 뷰 만의 특징임 -->

  <!-- 그러나 template에서는 해당 객체명 만으로 값에 접근 가능하다. -->

   <h1 :class="color">데이터 바인딩 {{ cnt }}</h1>
   <button type="button" @click="cnt++">증가</button>
   <button type="button" @click="cnt--">감소</button>
   <!-- HTML요소와 Vue 인스턴스의 데이터를 동적으로 연결하는 기능 -->
    <h3>{{ `${info.name} : ${info.age}` }}</h3>


  <!-- :class=" "를 해주면, 태그의 속성값을 데이터바인딩 할수 있다 -->
   <!-- 태그 속성명 앞에 `:` 을 붙이고 ,속성값에 데이터 바인딩 객체를 사용함 -->
  <h3 class="test" :class="color">태그 속성값 데이터 바인딩</h3>
  <button type="button" @click="btnToggle">색깔 토글</button>

  <!-- 양방향 데이터 바인딩. -->
   <input type="text" v-model="id">
   <p>{{ id }}</p>
</template>

<style>

 /* css 작성 부분 */
 .red{
  color: #ff0000;
 }
 .blue{
  color: #0000ff;
 }
</style>