<template>
  <h1>&lt;script setup&gt; tag</h1>
  <h3>script setup을 이용하면 components 옵션도 필요 없고
      setup함수를 만들 필요도 없으며, 명시적으로 변수를 반환하지 않아도 됨
  </h3>

  <input type="text" v-model="title" ref="msg" name="" id="">
  <button v-on:click="change">바꾸기</button>
</template>

<script setup>
const { ref }=require("@vue/reactivity");

    let title = ref('old title')
    const msg = ref(null)

    function change(){
        msg.value.value="new title"
        //msg가 ref로 설정이 되었기때문에 msg.value로 nsgm들고오고 
    }

    
</script>

<style>

</style>