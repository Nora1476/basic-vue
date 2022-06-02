<template>
  <h1>v-show</h1>
  <span>표현식 값의 참-거짓을 기반으로 엘리먼트의 display CSS 속성을 전환합니다.</span><br>
  <span v-show="flag" v-text="msg"></span>
</template>

<script>
const vm = {
    data: function(){return{msg:'Notice!!', flag:1}},
    methods:{
        toggle(){
            this.flag ^= true
        }
    },
    mounted (){
        setInterval(() => {
            this.toggle()
        }, 1000);
    }
}
export default  vm
 

</script>

<style>

</style>