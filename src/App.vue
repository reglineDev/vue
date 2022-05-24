<template>
  
  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modalOpen=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a, i) in menu" :key="i">{{ a }} {{ i }}</a>
  </div>


  <div v-for="(a, i) in products" :key="a">
    <h4>{{ products[i] }}</h4>
    <p>XX 만원</p>
    <button @click="신고Count[i]++">허위매물신고</button>
    <span>신고수 : {{ 신고Count[i] }}</span>
  </div>

  <div>
    <p>--------------------11111333333111-----------------------</p>
  </div>

  <div>
    <img :src="oneRooms[0].image" class="room-img">
    <h4 @click="modalOpen = true">{{ oneRooms[0].title }}</h4>
    <p> {{ oneRooms[0].price }} 만원</p>
    <button @click="increase(0)">허위매물신고</button>
    <span>신고수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <img src="./assets/room02.jpg" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>50 만원</p>
    <button @click="increase(1)">허위매물신고</button>
    <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <img src="./assets/room03.jpg" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>50 만원</p>
    <button @click="increase(2)">허위매물신고</button>
    <span>신고수 : {{ 신고수[2] }}</span>
  </div>
</template>

<script>

  import oneRoomData from './assets/oneroom.js';

  export default {
    name: 'App',
    data(){
      return{
        oneRooms : oneRoomData,
        modalOpen: false,
        신고Count : [0, 0, 0],
        신고수 : [0, 0, 0],
        menu : ['Home', 'Shop', 'About'],
        products : ['역삼동원룸', '천호동원룸', '마포구원룸']
      }
    },
    methods :{
      increase(arrNum){
        this.신고수[arrNum] += 1;
      }
    },

    component:{

    }
  }
</script>

<style>

  body{
    margin: 0;
  }

  div{
    box-sizing: border-box;
  }

  .black-bg{
    width: 100%; height: 100%;
    background: rgba(0, 0, 0, 0.5);
    position: fixed; padding:20px;
  }

  .white-bg{
    width: 100%; background: white;
    border-radius: 8px;
    padding: 20px;
  }

  .room-img{
    width: 300px;
    margin-top: 40px;
  }

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  .menu{
    background: darkslateblue;
    padding: 15px;
    border-radius: 5px;
  }
  .menu a{
    color: white;
    padding: 10px;
  }

</style>
