<template>

  <!--모달창-->
  <div class="black-bg" v-if="modalOpen==true">
    <div class="white-bg">
        <button class="x-btn" @click="modalOpen=false">X</button>
        <br>
        <h4>상세페이지</h4>
        <p>상세 내용</p>
    </div>
  </div>
  <!--모달창-->

  <div class="menu">
    <a v-for="menuNm in menuNmArr" :key="menuNm">{{menuNm}}</a>
    <!--<a v-for="(menuNm,i) in menuNmArr" :key="i">{{menuNm}}</a>-->
  </div>

  <div v-for="(products,i) in productsArr" :key="i">
      <img :src="require(`@/assets/room${i}.jpg`)" class="room-img">
      <h4 @click="modalOpen==false ? modalOpen=true : modalOpen=false">{{productsArr[i]}}</h4>
      <p>{{priceArr[i]}}만 원</p>
      <button @click="reportNumArr[i]++" @mouseover="logTest">허위매물신고</button> <!-- v-on: → @ -->
      <span>신고수: {{reportNumArr[i]}}</span>
  </div>
  
</template>

<script>

export default {
  name: "App",
  data(){
    return{
      reportNumArr: [0,0,0],
      priceArr: [60,100,150],
      productsArr: ['역삼동원룸','천호동원룸','마포구원룸'],
      colorRed: 'color:red',
      menuNmArr: ['Home','Products','About'],
      modalOpen: false
    }
  },
  methods: {
    logTest(){
      console.log('test')
    }
  },
  components: {
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.x-btn {
  float: right;
}
</style>
