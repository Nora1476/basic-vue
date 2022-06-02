<template>
    <div class="menu">
        <a v-for="nav in 메뉴들" :key="nav">{{nav}}</a>
    </div>

  <h1>v_conce</h1>
  <!-- v-once적용시 text적용해도 안바뀜 -->
  <span v-once>다시는 변경되지 않습니다.{{msg}}</span><br> 

  <!-- input창 text변경에 따라 일회성으로 같이 바뀜 -->
  <span>변경이 잘 됩니다.{{msg}}</span><br>
  <input type="text" v-model="msg"/>

</template>

<script>

export default {
   data(){
       return {
           msg: 'v-once이기 때문이죠',
           메뉴들: ['Home', 'Product', 'Price']
       }
   }
}

</script>

<style>
 .menu{
     background: darkslateblue;
     padding:15px;
     border-radius: 5px;
     color: beige;
 }
</style>