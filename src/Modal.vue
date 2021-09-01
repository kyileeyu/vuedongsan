<template>
    <div class="black-bg" v-if="modalOpen == true">
        <div class="white-bg">
            <h4> {{oneroom[click].title}}</h4>
            <img :src="oneroom[click].image" class="room">
            <p> {{oneroom[click].content}}</p>
            <input v-model="month">
            <p>{{month}}개월 선택함 : {{oneroom[click].price * month}}원 </p>
            <button @click="$emit('closeModal')">닫기</button>
        </div>
    </div>
</template>

<script>
export default {
    name : 'Modal',
    data(){
      return {
        month : 1, 
      }
    }, 
    props : {
        oneroom : Array,//자료형 대문자로
        modalOpen : Boolean,
        click : Number, 
    },
}
</script>

<style >
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
  .room{
    width: 50%;
  }
  
</style>