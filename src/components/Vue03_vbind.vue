<template>
  <div v-bind:id="dynamicId">Hello</div>  
  <img v-bind:src="url + '200x100'"/> <!--src 중복되면 에러뜸-->
  <div v-bind:class="[classA, classB]"></div>
  <div v-bind:style="[styleA, styleB]"></div>
  <div v-bind="{'id':'box', 'data-url':url}"></div> <!--속성 직접 추가-->
  <div id='box'  v-bind="{'data-url':url}"></div> <!--속성 직접 추가-->

  <!-- 위와 같은 코드
  <div :id="dynamicId">Hello</div>  
  <img :src="url + '200x100'"/> 
  <div :class="[classA, classB]"></div>
  <div :style="[styleA, styleB]"></div>
  <div :="{id:box, 'data-url':url}"></div> -->
  
</template>

<script>
export default {
    data(){
        return {
            dynamicId: "first-div", 
            url: "http://via.placeholder.com/",
            classA: "rect", 
            classB: "fill",
            styleA: "background:green; border-radius:50px", 
            styleB: "width:100px; height:100px; border:1px solid black",
        }
    }
}
</script>

<style>
    .rect{
        width:100px; height:100px;
        border: 1px solid red;
    }

    .fill {
        background:  blue;
    }   
</style>