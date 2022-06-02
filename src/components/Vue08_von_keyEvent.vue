<template>
  <h1>v-on keyEvent</h1>
  <button type="submit" @click="warning('Warning!!',$event)">Warning</button>  

</template>

<script>
export default {
    methods:{
        warning(msg,e){
            if(e) e.preventDefault();
            alert(e)
            alert(msg)
        }
    }
}
</script>

<style>

</style>