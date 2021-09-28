<template>
  <div id="app">
    <Main/>
    <h1 v-for="()">{{emailRandom}}</h1>
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

  axios.get("https://flynn.boolean.careers/exercises/api/random/mail")
  .then( (response) => {

    const result = response.data;
    console.log(result.response);
    this.emailRandom = result.response;

  });

},
 created(){
  
 }
}

</script>

<style lang="scss">


</style>
