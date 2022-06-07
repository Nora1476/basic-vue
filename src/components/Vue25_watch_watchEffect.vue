<template>
<h1>watch watchEffect</h1>
<h3>watch는 개발자가 코드로 지정한 변수의 값의 변화를 감시하는 것,
    콜백함수를 이용하여 부가적인 작업을 추가할 수 있다.
</h3>
  <p>{{count_o}}</p>
  <button @click="count_o++">Options API 카운트 증가</button>

  <p>{{count_c_1}}</p>
  <button @click="count_c_1++">Cpmposition API 1st 카운트 증가</button>

  <p>{{count_c_2}}</p>
  <button @click="count_c_2++">Cpmposition API 2dn 카운트 증가</button>

  <p>상태:{{state}}</p>
  <button @click="onStop()">watchEffect 중지</button>
</template>

<script>
import { ref, watch, watchEffect } from '@vue/runtime-core';
export default {
    //Options API
    data() {
        return{
            count_o:0,
        }
    },
    watch:{  //count_o 가 data 값도 가지지만 함수도 가짐(이전 값 (data)를 보고있음)
        count_o: function(cur, prev){
            console.log(`Options API Watch: ${prev} ==> ${cur}`);
        },
    },

    //composition API
    setup(){
        const count_c_1 = ref(0)
        const count_c_2 = ref(0)
        const state = ref('실행중')
      watch(
          count_c_1, function(cur, prev){
              console.log(`Composition API Watch: ${prev} ==> ${cur}`);
          }, //immediate:true 일 경우  초기값부터 변화(indefined -> 0)을 파악함
      )
      watch(
          [count_c_1, count_c_2], function(cur, prev){
              console.log(`Composition API Multiple Watch: ${prev} ==> ${cur}`);
          },{immediate:true,}
      )
      //watchEffect  불필요한 변수를 감시하지 않고 콜백함수에서 참조되는 변수만 감시
      const stop = watchEffect( //vue3 부터 나옴, 변수의 변화를 감지
          function(){
              console.log(`Composition API WatchEffect Called : ${count_c_2.value}`);
          },{flush:'post'} //post : dom이 업데이트 된 후에 콜백함수 호출
                          //pre : dom이 업데이트 하기 전에 콜백함수를 호출
      )
      const onStop= function(){
          state.value = '중지'
          stop()  //watchEffect를 할당받은 변수 stop을 함수로 호출stop()하면 watchEffect는 중단
      }
      return{count_c_1, count_c_2, state, onStop}
    }
}
</script>

<style>

</style>