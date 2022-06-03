<template>
  <h1>form element binding_ checkbox1</h1>
  <form action="">
      <input type="text" placeholder="edit me" v-model="message" >
      <p>Message is {{message}}</p>

    -----------------------------------------------------------------<br>

    <label for="checkbox"> 체크유무: {{ state }} </label>
      <input type="checkbox" id="checkbox" v-model="checked" v-on:change="checkit"><br><br>

    ----------------------------------------------------------------- <br> 


    <label for="banana"> 바나나 </label>
    <input type="checkbox" id="banana" v-model="selFruit" value="banana"><br>

    <label for="apple"> 사과 </label>
    <input type="checkbox" id="apple" v-model="selFruit"  value="apple"><br>

    <label for="pine_apple"> 파인애플 </label>
    <input type="checkbox" id="pine_apple" v-model="selFruit" value="pine_apple"><br>

 
    
    
    ----------------------------------------------------------------- <br> 
      <span>Multiline Message:</span>
      <p style="white-space:pre-line;">{{multiline}}</p>
      <textarea v-model="multiline" cols="30" rows="10"></textarea>
      <!-- <textarea cols="30" rows="10">{{multiline}}</textarea> 요라인은 vue 3.0에서는 작동X -->

  </form>
</template>

<script>
export default {
    data(){
        return{
            message:'누구인가?',
            multiline:'여러 줄을 작성합니다. \n\n',
            checked: true,       //체크박스 선택여부
            state: '동의함',
            selFruit:['banana','pine_apple','apple'],
        }
    },
    methods:{
        checkit(){
            this.state=(this.checked)?"동의함":"동의안함"
        }
    }
}
</script>

<style>

</style>