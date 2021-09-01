<template>

  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <h4> {{oneroom[click].title}}</h4>
      <img :src="oneroom[click].image" class="room">
      <p> {{oneroom[click].content}}</p>
        <p>{{oneroom[click].price}}원 </p>
      <button @click="modalOpen =false">닫기</button>
    </div>
  </div>


  <div class="menu">
      <a v-for="i in menu" :key="i">{{ i }}</a>
  </div>

  <Discount/>

  <img alt="Vue logo" src="./assets/logo.png">

  <div v-for="(a,i) in oneroom" :key="i">
    <img :src="a.image" class="room-img">
    <h4 @click="modalOpen = true; click = i">{{a.title}}</h4>
    <p>{{a.price}}원 </p>
  </div>


</template>

<script>

import data from './assets/oneroom.js';
import Discount from './Discount.vue';








export default {
  name: 'App',
  data(){//데이터 보관함 ==state라고 부름
    return {
      click : 0,
      oneroom : data,
      modalOpen : false,
      price : [50,60,70],
      menu : ["Home","Shop",'About'],
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
      cnt : [0,0,0],
    }
  },
  methods : {

  },

  components : {
    Discount : Discount,//보통은 이렇게 맞춰씀
  },
}
</script>

<style>
body{
  margin : 0;
}


div {
  box-sizing: border-box;
}

.black-bg {
  width : 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding : 20px;
}

.white-bg {
  width : 100%;
  background: #fff;
  border-radius: 8px;
  padding : 20px;
}
.room-img{
  width : 100%;
  margin-top : 40px;
}

.room{
  width: 50%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu{
  background-color: rgb(110, 103, 158) ;
  padding : 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
