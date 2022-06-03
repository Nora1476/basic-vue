<template>
  <div :class="footer">
      Vue3 exercise
  </div>
  </template>

<script>
export default {
    data(){
        return{
            footer:"footer",
        }
    }
}
</script>

<style>
.footer{
 height: 100px;
 margin: 0;
 background: rgb(234, 218, 243);
 line-height: 90px;
 padding-left: 50px;
 font-weight: bold;
}
</style>