<template>
  <h1>select binding Options API</h1>
  select는 바인딩을 할 때 option의 value에 binding을 한다.
  <select name="selItem" ref="selItem" id="selItem" v-model="selected" v-on:change="selChange">
    <option value="반지">ring</option>
    <option value="목걸이">necklace</option>
    <option value="귀걸이">earring</option>
    <option value="시계">watch</option>
    <option value="팔찌">bracelet</option>
  </select><br>
  <span>{{selected}} / {{selectText}}</span><br>
  <span>{{selected}} / <span ref="selText" id="selText"></span></span>
</template>

<script>
// import { onMounted } from '@vue/runtime-core';
export default {
  // Options API 방식 :: Vue2.x
  data: ()=>({selected: '목걸이',selectText: ''}),
  methods: {
    selChange(){
      // const sel = e.target;
      // const selText = this.$refs.selText
      // this.selectText = sel.options[sel.selectedIndex].text;
      // selText.textContent = sel.options[sel.selectedIndex].text;
      this.getSelText()
    },
    getSelText() {
      // $refs 접근
      const selItem = this.$refs.selItem
      const selText = this.$refs.selText
      this.selectText = selItem.options[selItem.selectedIndex].text
      selText.textContent = selItem.options[selItem.selectedIndex].text

      //dom 접근 _ sapn 태그 접근
      // const selItem = document.querySelector("#selItem")
      // const selText = document.querySelector("#selText")
      // this.selectText = selItem.options[selItem.selectedIndex].text  //data 값 selectText값을 들고옴
      // selText.textContent = selItem.options[selItem.selectedIndex].text
    },
  },
  mounted : function() {
    this.getSelText();
  }

}
</script>

<style>

</style>