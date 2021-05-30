<template>
  <div id="home">
    {{txt}}
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  data(){
    return{
    txt: 'Hi there'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
