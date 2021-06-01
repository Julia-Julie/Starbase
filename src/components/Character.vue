<template>
  <div class="character">
    <pre>
      {{ character }}
      </pre
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      character: {},
    };
  },

  methods: {
    getCharachers() {
      fetch("https://swapi.dev/api/people/1", {
        method: "Get",
      })
        .then((response) => response.json())
        .then((json) => (this.character = json));
    },
  },

  created() {
    this.getCharachers();
  },
};
</script>

<style lang="sass"></style>
