<template>
  <h1>v-for</h1>
    <ul class="city">
        <!-- inx는 인덱스번호 필수값은 아님-->
        <li v-for="item in list" :key="item"> {{item}} </li> <br>
        <li v-for="(item, idx) in list" :key="idx"> {{idx+1}}. {{item}} </li> 
    </ul>

    <ul class="gugu">
        <!-- 2 -->
        <!-- <li v-for="item in i" :key="item"> 2*{{item}} ={{2*item}}</li> -->

        <!-- 2중 for문 -->
        <li v-for="item in i" :key="item"> <br>
            <ul>
                <li v-for="item2 in j" :key="item2">{{item}}*{{item2}} = {{item*item2}}</li> 
            </ul>
        </li>  

    </ul>
        
        
        <span v-for="item in i" :key="item"> <br>
                <span v-for="item2 in j" :key="item2">{{item}}*{{item2}} = {{item*item2}}  </span> 
        </span>
    
</template>

<script>
export default {
    data() {
        return {
            list:['Busan', 'Seoul', 'Changwon', 'Pohang', 'Incheon'],
            i:[2,3,4,5,6,7,8,9],
            j:[1,2,3,4,5,6,7,8,9]
        }
    }
}
</script>

<style>
    .city li,
    .gugu li{
        list-style: none;
    }

</style>