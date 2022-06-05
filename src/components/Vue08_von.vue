<template>
  <h1>v-on</h1>
  <!-- <button v-on:click="count++">Add 1</button> -->
  <!-- <button v-on:click="doThis">Add 1</button> -->

  <!-- 아래와 같은코드 
 <button @click="doThis">Add 1</button>
  <p>위 버튼을 클린한 횟수는 {{count}}</p>
  <input type="text" name="txt" id="txt" 
            @mouseout="reverse" 
            @mouseenter="reverse" 
            v-bind:value="msg"> -->

  <button @click="doThis">Add 1</button>
  <p>위 버튼을 클린한 횟수는 {{count}}</p>
  <input type="text" name="txt" id="txt" v-bind:value="msg" 
        v-on="{mouseout:reverse, mouseenter:reverse }"/>  
        <!-- 이벤트 여러개 적용시킬때 -->


  <form action="http://127.0.0.1:8080" method="post">
    <input type="text" name="name" ref="yourName">
    <!-- ref : element나 자식컴포넌트에 대한 참조를 등록할떄 사용-->
    <button @click.prevent.once="isName" type="submit">확인</button>
    <!-- prevent,stop(버블링 막음), once(이벤트를 한번만 적용)은 각각 적용가능 -->
  </form>

</template>

<script>
export default {
    data() {
        return{
            count:0,
            msg:'Hello vue3',
            nameStr:"",
        }
    },
    methods: {
        doThis(){
            this.count++
        },
        reverse(){
            this.msg= this.msg.split('').reverse().join("");
        },
        isName(){
            const name=this.$refs.yourName      //ref를 $ 사용하여 땡겨옴  
            if(name.value===""){                //유효성검사
                alert("name을 확인하여 주세요.")
                name.focus()
                return 
            }
        }
    }

}
</script>

<style>

</style>