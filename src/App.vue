<template>
  <div id="app">
    <Main/>
    <!-- <h1>{{emailRandom}}</h1> -->
    <!-- <h1>{{emailList}}</h1> -->
      <div class="my-v-if" v-if="emailList.length == 10">
        <ul>
          <li v-for="(email, index) in emailList" :key="index">
            {{email}}
          </li>
        </ul>
      </div>
  </div>
</template>

<script>
import Main from './components/Main.vue';
import axios from "axios";


export default {
  name: 'App',
  components: {
    Main,
  },
  data: function () {
    return{
      emailRandom : "",
      emailList : [],
    }
  },
mounted() {
  // let self = this;
  console.log(axios);
  
  for (let i = 0; i < 10; i++) {
    axios.get("https://flynn.boolean.careers/exercises/api/random/mail")
    .then( (res) => {
      console.log(res);
      const result = res.data;
      console.log(result);
      this.emailRandom = result.response; 
      this.emailList.push(this.emailRandom);     

      console.log(this.emailRandom) 
      console.log(this.emailList)
    });
  }
},
 created(){
  
 }
}

</script>

<style lang="scss">


</style>
