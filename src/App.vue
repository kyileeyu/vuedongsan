<template>

  <Modal @closeModal="modalOpen = false" :oneroom="oneroom" :modalOpen="modalOpen" :click="click"/>


  <div class="menu">
      <a v-for="i in menu" :key="i">{{ i }}</a>
  </div>

  <Discount/>

  <img alt="Vue logo" src="./assets/logo.png">  

  <Card @openModal="modalOpen = true; click= $event" :room="oneroom[i]"  v-for="(작명,i) in oneroom" :key="작명"/>
   

</template>

<script>

import data from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Cardlist.vue';





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
    Modal : Modal,
    Card : Card,
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
