<template>
  <h1>Form element fadio binding</h1>
  <label for="radioA">A</label>
  <input type="radio" name="radio" id="radioA" v-model="pick" v-bind:value="A">
  <label for="radioB">B</label>
  <input type="radio" name="radio" id="radioB" v-model="pick" v-bind:value="B">
  <label for="radioC">C</label>
  <input type="radio" name="radio" id="radioC" v-model="pick" v-bind:value="C">
<br>
  <span>{{pick}}</span>

  <input type="hidden" name="choice" v-text="pick">

</template>

<script>
export default {
    data(){
        return{
            pick:"어린이",
            A:"어린이",
            B:"청년",
            C:"중년"
        }
    }
}
</script>

<style>

</style>