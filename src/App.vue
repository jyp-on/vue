<template>
  <div>
    <div class="black-bg" v-if="모달창상태 == true">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p>상세페이지 내용</p>
        <button @click="모달창상태 = false">닫기</button>
      </div>
    </div>


    <div class=menu>
      <a v-for="(menu,index) in 메뉴들" :key="index" href="">{{menu}}</a>
    </div>
    <div v-for="(value, index) in products" :key="index">   
      <img src="./assets/room0.jpg" class="room-img" alt="">
      <h1 @click="모달창상태 = true">{{value}}</h1>
      <p>50 만원</p>
      <button @click="신고수[index]++">허위매물신고</button> <span>신고수 : {{신고수[index]}}</span>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      모달창상태: false,
      신고수 : [0,0,0],
      메뉴들 : ['Home', 'Products', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : {
    increase(){
      this.신고수[0]++
    },
  },

  components:{

  }
}


</script>

<style>
body{
  margin:0
}
div{
  box-sizing: border-box;
}
.black-bg{
  width:100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width:70%; background: white;
  margin: 0 auto;
  border-radius: 8px;
  padding:20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background:darkslateblue;
  padding:15px;
  border-radius:15px;
}
.menu a{
  color: white;
  padding: 10px;
}
.room-img{
  width:60%;
  margin-top:40px;
}
</style>
