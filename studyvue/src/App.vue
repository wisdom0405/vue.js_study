<template>

  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{menu}}</a>
  </div>

  <div>
    <h4 class="red" :style="styleblue">{{products[0]}}</h4>
    <p>{{price1}}만원</p>
    <button @click="신고수++">허위매물신고</button> <span>신고수 : {{신고수}}</span>

  </div>
  <div>
    <h4 class="red" :style="styleblue">{{products[1]}}</h4>
    <p>{{price2}}만원</p>
  </div>
  <div>
    <h4 class="red" :style="styleblue">{{products[2]}}</h4>
    <p>{{price2}}만원</p>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      // 데이터 보관 (데이터는 object자료로 저장 : {자료이름 : 자료내용})
      price1:60,
      price2:70,
      styleblue: 'color : blue',
      menus : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : 0
    }
  },
  components: {

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
.menu {
  /* menu class의 스타일 지정 */
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  /* menu class의 a태그 스타일 지정 */
  color: white;
  padding: 10px;
}
</style>
