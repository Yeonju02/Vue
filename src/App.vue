<template>

  <!-- <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>내용</p>
    </div>
    <button @click="모달창열렸니 = false">닫기</button>
  </div> -->


  <ModalOpen v-bind:state="모달창열렸니"/>


  <div class="menu">
    <a v-for="i in menus" :key="i"> {{ i }} </a>
  </div>


  <div v-for="i in onerooms" :key="i">
    <img :src="i.image " class="room-img">
    <h4 @click="모달창열렸니 = true">{{ i.title }}</h4>
    <p>{{ i.price }}원</p>
  </div>
  


</template>

<script>

import data from './assets/oneroom.js';
import ModalOpen from './components/ModalOpen.vue';

export default {
  name: 'App',
  components: {
    ModalOpen
  },
  data() {
    return {
      onerooms : data,
      모달창열렸니 : false,
      신고수 : [0, 0, 0],
      menus : ['Home', 'Shop', 'About']

    }
  }
}
</script>

<style>

body {
  margin : 0
}
div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px ;
}

.room-img {
  width: 50%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}


</style>
