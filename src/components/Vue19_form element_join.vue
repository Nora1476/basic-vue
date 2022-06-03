<template>
  <h1>form element Join</h1>
  <form action="Vue20_memberList.vue" ref="frm">
    <fieldset>
        <legend>회원 가입</legend>
        <div>
            <label for="id" class="title"> ID </label>
            <input type="text" ref="id" id="id">
        </div>
        <div>
            <label for="name" class="title"> Name </label>
            <input type="text" ref="name" id="name">
        </div>
        <div>
            <label for="pass" class="title"> Password </label>
            <input type="password" ref="pass" id="pass">
        </div>
        <div>
            <label for="repass" class="title"> Re Password </label>
            <input type="password" ref="repass" id="repass">
        </div>
        <div>
            <label class="title">Hobby</label>
            <label :for="item" v-for="(item, i) in hobbyList" :key="i"> {{item}} 
                <input type="checkbox" name="hobby" :id="item" :value="item" v-model="hobby"> 
            </label>  <!--Hobby 는 필수값이 아니기 때문에 ref없어도됨-->
        </div>
        <div>
            <label class="title"> Gender </label>
             <label :for="item" v-for="(item, i) in genderList" :key="i"> {{item}} 
                <input type="radio" name="gender" :id="item" :ref="item" :value="item" 
                 v-model="gender"> 
            </label>
        </div>
        <div>
            <label for="mobile" class="title"> Mobile </label>
            <select v-model="mobile" ref="m1" id="mobile" name="mobile">
                <option :value="item" v-for="(item, i) in mobileList" :key="i">{{item}}</option>
            </select>
            -<input type="text"  ref="m2" class="m">
            -<input type="text"  ref="m3" class="m">
            <input type="hidden" ref="mobile" name="mobile" >
        </div>
        <div>
            <label class="title"> </label>
            <button ref="btnJoin" @click="join($event)" class="btn_margin"> 가입 </button>
            <button ref="btnCancel" @click="cancel"> 취소 </button>
        </div>
    </fieldset>
  </form>
</template>

<script>
export default {
    data(){
        return{
            hobby:[],
            hobbyList:['축구','배구','농구'],
            gender:'여',
            genderList:['남','여'],
            mobile:"010",
            mobileList:['010', '011', '016']
        }
    },
    methods:{
        join(e){
            const frm = this.$refs.frm
            const id = this.$refs.id
            const name = this.$refs.name
            const pass = this.$refs.pass
            const repass = this.$refs.repass
            const m2 = this.$refs.m2
            const m3 = this.$refs.m3
            //const mobile = this.$refs.mobile
            if(e) e.preventDefault();
            if(id.value ===""){
                alert("ID을 확인하여 주세요.")
                id.focus()
                return 
            }
            if(name.value ===""){
                 alert("Name을 확인하여 주세요.")
                name.focus()
                return 
            }
            if(pass.value ===""){
                 alert("Password를 확인하여 주세요.")
                pass.focus()
                return 
            }
            if(pass.value !== repass.value){
                 alert("Password가 일치하지 않습니다.")
                repass.focus()
                return 
            }
            if(m2.value ===""){
                 alert("Mobile 번호를 확인하여 주세요.")
                m2.focus()
                return 
            }
            if(m3.value ===""){
                 alert("Mobile 번호를 확인하여 주세요.")
                m3.focus()
                return 
            }
            
            frm.submit()
            
        },
        cancel(){
            const frm = this.$refs.frm
            const radioFemale = this.$refs.여
            frm.reset()
            radioFemale.checked = true
        }
    }
}
</script>

<style>
.title {
    display: inline-block;
    width: 110px;
    margin: 5px;
    text-align: left;
}
fieldset div{
    width: 100%;
    text-align: left;
}

.m {
    width: 50px;
}
.btn_margin{
    margin: 20px 30px;
}
</style>