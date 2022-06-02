<template>
  <h1>v-on key event</h1>
  <!-- <input type="submit" value="Send" v-on:keyup.enter="send"> -->
  <input type="submit" value="Send" v-on="{ 'keyup.enter':send, click:send }">
  enter키와 클릭할 때 반응<br>
  
  <input type="text" v-on:keyup='keyPressed1($event)'>
  모든 키 반응 String.fromCharCode()으로 숫자와 알파벳만 문자로 변환<br><br>

  <input type="text" v-on:keyup.page-down='keyPressed2($event,"Page Down")'>
  String.fromCharCode() 미적용 특정키 만 반응(page down)<br><br>

  <input type="text" v-on:keyup.exact.alt.shift="onMix1" > 
  alt shift exact => working, alt shift no =>not working<br><br>

  <input type="text" v-on:keyup.exact.alt.shift="onMix1"
    v-on:keyup.exact.page-up="onMix2"> 
  alt shift exact, page-up exact => 모든 키에 onMix1 한번만 호출<br><br>

  <input type="text" v-on:keyup.exact.alt.shift="onMix1"
    v-on:keyup.page-up="onMix2"> 
  alt shift exact, page-up no  => page-up 키에 onMix1, onMix2 둘 다 동작/
                                  그외 다른키에는 onMix1만 동작<br><br>

  <input type="text" v-on:keyup.alt.shift="onMix1"
    v-on:keyup.exact.page-up="onMix2"> 
  alt shift no, page-up exact    <br><br>
  
  alt shift no, page-up no => not working<br><br>
  <!-- <input type="text" v-on:keyup.alt.shift="onMix1" v-on:keyup.page-up="onMix2"> -->

  <input type="text" v-on:keyup.meta="onMeta"> meta

</template>

<script>
export default {
  methods: {
    send() {console.log('enter key가 눌러졌습니다.')},
    keyPressed1(e) {console.log(String.fromCharCode(e.keyCode)+' is pressed')},
    keyPressed2(e,caption) {console.log(caption+"("+(e.keyCode)+') is pressed')},
    onMix1() {console.log("1복합 클릭했어요");},
    onMix2() {console.log("2복합 클릭했어요");},
    onMeta() {console.log("윈도우키를 누르고 키를 눌렀어요");},
  }
}
</script>

<style>

</style>