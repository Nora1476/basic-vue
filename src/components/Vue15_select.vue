  <template>
    <h1>form element binding_ select</h1>

        <p>select의 옵션에 value값을 넣지 않으면 text값이 value가 됨.</p>

        <select v-model="selected">
            <option value="" disabled>Please select one</option>
            <option value="에라이">A</option>
            <option>B</option>
            <option>C</option>
        </select><br>
        <span>{{selected}}</span><br><br>
-----------------------------------------------------------------------------------------<br><br>
        <select v-model="arrSelect">
            <option value="" disabled>Please select one</option>
            <option v-for="(item,i) in arrObj" :key="i" :value="item.value">{{item.text}}</option>
        </select><br>
         <span>{{arrSelect}}</span><br><br>

  </template>
  
  <script>
  export default {
      data() {
          return{
              selected:"A",
              arrSelect:"C",
              arrObj:[{text:'One', value:'A'},
                   {text:'Two', value:'B'},
                   {text:'Three', value:'C'},
                   {text:'Four', value:'D'},],
          }
      }
  }
  </script>
  
  <style>
  
  </style>