<template>
  <h1>v-on capture, self</h1>
  <div v-on:click="doTop" id="top">
       <div v-on:click.self="doMiddle" id="middle">
           <!-- <button type="button" v-on:click.stop="doBottom">Bubble</button> -->
           <button type="button" v-on:click="doBottom">Bubble</button>
       </div>
  </div>
  stop은 자신만 이벤트를 실행할 경우 버블링방지<br>
  capture는 parent가 먼저 실행되어야될 경우 자신이 아닌 parent에 붙여사용<br>
  상위 노드에 capture가 연속적일 경우 마지막으로 적용된 노드가 먼저 시작.<br><br>

  self는 하위 버블링의 영향을 받지않음
  본인 이벤트 발생시에만 작동

 
</template>

<script>
export default {
    methods: {
        doTop (){
            console.log('Top 이벤트 발생');
        },
        doMiddle(){
            console.log('Middle 이벤트 발생');

        },
        doBottom(){
            console.log('Bottom 이벤트 발생');
        }
    }
}
</script>

<style>

#top {
    width:200px;
    height: 200px;
    background: green;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
}

#middle{
    width:100px;
    height: 100px;
    background: yellow;
    display: flex;
    justify-content: center;
    align-items: center;
}

</style>