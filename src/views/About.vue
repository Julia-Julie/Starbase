<template>
  <div class="about">
    <h1 class='about__headline'>{{ headline }}</h1>
  </div>
</template>

<script>

export default {
  name: "About",
    data() {
      return {
        headline: "About Notemaster App",
       
      };
    },
};
</script>

<style scoped lang="scss">
.about{
  &__headline{
    color: red;
  }

  &__content{
    color: purple;
  }


}


</style>
