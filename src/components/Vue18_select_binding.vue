<template>
  <h1>form element binding _select2</h1>

<p>select는 바인딩을 할 때 option의 value에 binding을 한다. </p>

  <select name="selItem" ref="selItem" id="selItem" v-model="selected" v-on:change="selChange">
      <option value="반지">ring</option>
      <option value="목걸이">necklace</option>
      <option value="귀걸이">earing</option>
      <option value="팔찌">bracelet</option>
      <option value="시계">watch</option>
  </select>
<br>
  <span>{{selected}}/{{selectText}}</span>
</template>

<script>
import { onMounted } from '@vue/runtime-core';
export default {
    data(){
        return{
            selected:"시계",
            selectText:"watch",   
        }
    },
    methods:{
        selChange(e){
            const sel =e.target
            console.log(sel.value);
            console.log(sel.options[sel.selectedIndex].text)
            this.selectText =sel.options[sel.selectedIndex].text 
            //this를 통해 data객체의 selectText 값에 접근하여 값을 변경
        },
        // getSelText() {
        //   const selItem = this.$refs.selItem;
        //   this.selectText = selItem.options[selItem.selectedIndex].text;
        //   console.log(this.selectText);
        // }
        
    },
    setup() {
    const start = (function() {this.getSelText()});
    const getSelText= (function() {
      console.log('hello');
    })
    onMounted(() =>{
      getSelText()
    })
    return {
      start, getSelText
    }
    
  }, 
}
</script>

<style>

</style>