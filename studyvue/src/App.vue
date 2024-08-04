<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">  
      <h4>상세 페이지임</h4>
      <p>상세 페이지 내용임</p>
    </div>
    <button @click="모달창열렸니 = false">닫기</button>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{menu}}</a>
  </div>

  <div>
    <img :src="원룸들[0].image" class="room-img">
    <h4>{{원룸들[0].title}}</h4>
    <p>{{원룸들[0].title}}</p>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4 >{{products[1]}}</h4>
    <p>{{price2}}만원</p>
    <button @click="신고수[1]++">허위매물신고</button> 
    <span>신고수 : {{신고수[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 >{{products[2]}}</h4>
    <p>{{price2}}만원</p>
    <button @click="신고수[2]++">허위매물신고</button> 
    <span>신고수 : {{신고수[2]}}</span>
  </div>
</template>

<script>
import data from './assets/oneroom.js';

export default {
  name: 'App',
  data(){
    return{
      // 데이터 보관 (데이터는 object자료로 저장 : {자료이름 : 자료내용})
      menus : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0,0,0],
      모달창열렸니 : true,
      원룸들 : data
    }
  },
  methods : {
    increase(){
      // Vue에서 함수만들 때 주의사항 : 함수안에서 데이터 쓸 땐 this.데이터명
      this.신고수 += 1;
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
.room-img{
  width: 100%;
  margin-top: 40px;
}
body{
  margin : 0
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
