<template>
    <h1>form element binding_ radio</h1>
    <!-- <p>라디오에서 value값은 v-model로 선택되었을때 활용 됨. 반드시 필요함!</p> 
    <p>라디오는 한개만 선택되기 때문에 data값으로 배열이 아니고 문자열 하나만 들어감!</p>  -->
    <label for="one"> one</label>
    <input type="radio" name="radio" id="one" value="one" v-model="picked">
    <label for="two"> two</label>
    <input type="radio" name="radio" id="two" value="two" v-model="picked">
    <p>Picked : {{picked}}</p>

</template>

<script>
export default {
    data(){
        return {
            picked:"one"
            //"v-model을 이럴때 쓰는구먼 radio box 클릭해보세요ㅋ"
        }
    }
}
</script>

<style>
</style>