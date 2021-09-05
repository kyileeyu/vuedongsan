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
    watch :{
      month(a){
        if(a >=13) alert('13이상 하지마셈');
        //month 라는 데이터가 변할 때마다 여기있는 코드를 지나감
        if(isNaN(a)){
          alert('숫자만 입력하세요');
          this.month=1;
        }
        if(a==2)alert('3달부터 신청하실 수 있습니다')
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
.start {
  opacity: 0;
  transition : all 1s;
}
.end{
  opacity:1;
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
  .room{
    width: 50%;
  }
  
</style>