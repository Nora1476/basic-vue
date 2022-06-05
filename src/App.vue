<template>
  <img alt="logo image" src="./assets/logo.png" width="50" /><br>
  <h1>Exercise</h1>

  <div class="container">
    <div v-bind:class="classCard" v-for="(component,i) in arrList" :key="i">
        <span v-text="i+1"></span>
        <component v-bind:is="component"></component>
    </div>
  </div>
 
 <footer><Footer mag="Footer for Your Vue.js"/></footer>
</template>

<script>
// import 이름 다르게해서 여러게 동시에 연결가능
import Exercise1 from './components/Vue01_data.vue'
import Exercise2 from './components/Vue02_declaritive_rendering.vue'
import Exercise3 from './components/Vue03_vbind.vue'
import Exercise4 from './components/Vue04_vonce.vue'
import Exercise5 from './components/Vue05_vshow.vue'
import Exercise6 from './components/Vue06_vif.vue';
import Exercise7 from './components/Vue07_vfor.vue';
import Exercise8 from './components/Vue08_von_keyEvent.vue';
import Exercise88 from './components/Vue08_von.vue';
import Exercise9 from './components/Vue09_von_Event.vue';
import Exercise10 from './components/Vue10_von_keyEvent_강사님.vue';
import Exercise11 from './components/Vue11_von_mouseEvent.vue';
import Exercise12 from './components/Vue12_von_capture_self.vue';
import Exercise13 from './components/Vue13_checkbox.vue';
import Exercise14 from './components/Vue14_radio.vue';
import Exercise15 from './components/Vue15_select.vue';
import Exercise16 from './components/Vue16_checkbox.vue';
import Exercise17 from './components/Vue17_radio_binding.vue';
import Exercise18 from './components/Vue18_select_binding.vue';
import Exercise19 from './components/Vue19_form element_join.vue';

import Footer from './components/Vue_Footer.vue';

export default {
  name: "App",
  components: {
    Exercise1,Exercise2,Exercise3,Exercise4,Exercise5,
    Exercise6,Exercise7,Exercise8,Exercise88,Exercise9, 
    Exercise10,Exercise11,Exercise12,Exercise13,Exercise14,
    Exercise15,Exercise16,Exercise17,Exercise18, Exercise19,
    Footer
  },
  data() {
    return{
      arrList:[Exercise1,Exercise2,Exercise3,Exercise4,Exercise5,
      Exercise6,Exercise7,Exercise8,Exercise88,Exercise9, 
      Exercise10,Exercise11,Exercise12,Exercise13, Exercise14, 
      Exercise15,Exercise16,Exercise17,Exercise18, Exercise19 ],
      classCard:"card"
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

/* .container {
  display: grid;
  grid-template-columns: repeat(2, 1fr)
} */

/* .card {
  border: 1px solid black;
  margin :10px;
  padding: 10px;
  height: 500px;
  overflow: auto;
} */
.container {
  overflow: hidden;
}
.card {
  border: 1px solid black; 
  border-radius: 5%;
  float:left;
  margin: 5px; padding:10px;
  width: 500px; height: 500px; overflow: auto;
}

</style>
