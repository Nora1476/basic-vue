<!-- <template>
  <h1>Options API data</h1>
  <button @click="count++">count is: {{count}}</button>
</template>
<script>
export default {
  data() {
    return {count: 0}
  }
}
</script> -->

<!--<template>
  <h1>Options API data, methods</h1>
  <button @click="addOne">Add</button>
  <span ref="result">count is:</span>
</template>
<script>
export default {
  data() {
    return {count: 0}
  },
  methods:{
    addOne : function(){
      this.$refs.result.textContent = `count is: ${++this.count}`
    }
  }
}
</script>-->

<!--<template>
  <h1>Composition API ref</h1>
  <button @click="addOne">Add</button>
  <span ref="result">count is:</span>
</template>
<script>
 import { ref } from '@vue/reactivity';
export default {
 
  setup(){
    //state data, 변수 값 설정
    const count= ref(0) //count 변수를 0으로 초기화

    //refs
    const result =ref(null) //sapn 태그를 초기화

    //methods
    function addOne(){
      result.value.textContent =`count is:${++count.value}`
      // result.value. 기본적으로 불러올값을 지정
    }

    return{count, result, addOne}
  }
}
</script>-->

<template>
  <h1>Composition API reactive</h1>
  <button @click="addOne">Add</button><br>
  <span ref="result">count is:{{count}}</span>
</template>
<script>
 import { reactive, ref } from '@vue/reactivity';
export default {
 
  setup(){
    //복수개의 변수를 하나의 변수로 리턴하고자 할때
    //options API에서 data의 역할
    const state = reactive({
      count : 0,
    })

    const result =ref(null) //sapn 태그를 초기화

    function addOne(){
      result.value.textContent =`count is:${++state.count}`
    }

    return{state, result, addOne}
  }
}
</script>