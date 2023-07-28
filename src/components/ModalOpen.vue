<template>
  <div class="black-bg" v-if="state == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>내용</p>
    </div>
    <button @click="모달창열렸니 = false">닫기</button>
  </div>
</template>

<script>
export default {
    props : ['state']
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
</style>