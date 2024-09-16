<template>

  <div class="menu">
    <a v-for="menuNm in menuNmArr" :key="menuNm">{{menuNm}}</a>
    <!--<a v-for="(menuNm,i) in menuNmArr" :key="i">{{menuNm}}</a>-->
  </div>

  <img alt="Vue logo" src="./assets/logo.png" />

  <div>
      <h4 :style="colorRed">{{products[0]}}</h4>
      <p>{{price1}}만 원</p>
  </div>
  <div>
      <h4>{{products[1]}}</h4>
      <p>{{price2}}만 원</p>
  </div>
</template>

<script>

export default {
  name: "App",
  data(){
    return{
      price1: 60,
      price2: 100,
      products: ['역삼동원룸','천호동원룸','마포구원룸'],
      colorRed: 'color:red',
      menuNmArr: ['Home','Products','About']
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
</style>
