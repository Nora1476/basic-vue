<template>
  <h1>v-on mouse event</h1>
  <!-- <input type="button" value="마우스 왼쪽" v-on:click.left="mouse_left"> -->
  <!-- <input type="button" value="마우스 왼쪽" v-on:click.right="mouse_right"> -->
  <!-- <input type="button" value="마우스 왼쪽" v-on:click.middle="mouse_middle"> -->

  <input type="button" value="마우스 왼쪽 가운데 오른쪽" v-on:click.left="mouse_left"
    v-on:click.right="mouse_right" v-on:click.middle="mouse_middle"
    v-on:contextmenu="mouse_right" > <br><br>

  exact는 보조키로써 다른키와 같이 눌렀을 때 동작(alt, shift에 적용)<br><br>
  <input type="text" v-on:click.exact.alt.shift="onMix1"><br>
  alt shift exact<br>
  alt+shift+클릭했을때만 onMix1<br><br>
  
  <input type="text" v-on:click.exact.alt.shift="onMix1" v-on:click.exact="onMix2"><br>
  alt shift exact, mouse exact<br>
  alt+shift+클릭= onMix1함수실행 / 클릭만했을경우 onMix2 함수실행<br><br>
  
  <!-- <input type="text" v-on:click.exact.alt.shift="onMix1" v-on:click="onMix2"> --> 
  alt shift exact, mouse no 클릭키 이벤트 중복으로 안됨<br>
  
  <!-- <input type="text" v-on:click.alt.shift="onMix1" v-on:click="onMix2">  -->
  alt shift no exact, mouse no exact 클릭키 이벤트 중복으로 안됨<br>
  
</template>

<script>
export default {
  methods:{
    mouse_left(){console.log("마우스 왼쪽 버튼을 눌렀어요");},
    mouse_right(){console.log("마우스 오른쪽 버튼을 눌렀어요");},
    mouse_middle(){console.log("마우스 가운데 버튼을 눌렀어요");},
    onMix1() {console.log("1복합 클릭했어요");},
    onMix2() {console.log("2복합 클릭했어요");},
   }
}
</script>

<style>

</style>