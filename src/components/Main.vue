<template>
  <div>
    <ul>
      <li v-for="(email, index) in emailList" :key="index">
        {{email}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Main',
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
