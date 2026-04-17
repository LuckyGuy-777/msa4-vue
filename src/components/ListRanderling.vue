<script setup>
import axios from 'axios';
import { ref} from 'vue';


const arr = [3,4,2,5];

const data = ref([]);

async function getPicsum(){
  try{

    const url = 'https://picsum.photos/v2/list?page=4&limit=7';
    const res = await axios.get(url);
    // data의 뒤에 추가.
    data.value.push(...res.data);
  } catch(error){
    console.log(error);
  }
}

</script>

<template>
  <h1>리스트 렌더링</h1>
  <button type="button" @click="getPicsum">추가</button>

  <div class="container">
    <div class="card" v-for="item in data" :key="item.id">
    <div class="card-Img" :style="{backgroundImage: `url('${item.download_url}')`}"></div>
    <span>{{ item.author }}</span>
    </div>
  </div>

  <!-- 뷰에서 배열 순회 방법. 전역변수 arr의 요소를 모두 찍어줌 -->
   <!-- 아래 처럼, key를 주면, 인덱스도 부여할수 있다. -->

   <!-- div 자체를 반복해서 생성함. -->
  <div v-for="(val, key) in arr" :key="key">
    <p>{{ val }}</p>
  </div>

  <div v-for="value in 5">
    <p>{{value}}회</p>
  </div>
</template>

<style scoped>
/* scoped 란? 스타일들의 전파 현상을 막기 위해서 사용. */

.container {
  padding: 20px;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 10px;
}

.card{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 10px;
}

.card-Img{
  padding-top: 60%;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

</style>