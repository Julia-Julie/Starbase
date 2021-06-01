<template>
  <div class="home">
    <h1>{{title}}</h1>
    <h2>{{subtitle}}</h2>
    <div class="character__list">
      <character
    v-for="(id, index) in this.initial_ids"
    v-bind:id="id"
    v-bind:key="index"
    />
    </div>
  </div>
</template>

<script>
import Character from '../components/Character.vue';

export default {
  name: "Home",

  data() {
    return {
      title: "Choose one of the charecter of Star Wars",
      subtitle: "Click on them to see more ones",
      initial_ids: [1, 2, 3]
    };
  },

  components:{
    Character
  },



  // methods: {
    // getCharachers() {
    //   fetch("https://swapi.dev/api/people/1", {
    //     method: "Get",
    //   })
    //     .then((response) => console.log(response))
    //     .then(response => response.text())
    //     .then(response => response.blob())
    //     .then((response) => response.json())
    //     .then((json) => console.log(json));
    // },
  // },
};
</script>

<style scoped lang="scss">
// Variables
$primary-color: violet;
$secondary-color: rgb(80, 0, 80);
$filled-bg: lavenderblush;
$red-color: rgb(107, 18, 18);

@mixin flex-align($horizontal, $vertical) {
  display: flex;
  flex-wrap: wrap;
  justify-content: $horizontal;
  align-items: $vertical;
}

// Reset styles
input,
select,
textarea,
button,
::placeholder {
  all: unset;
  outline: none;

  &:focus {
    all: unset;
  }
}

.container {
  max-width: 1100px;
  margin: 0 auto;
}

.btn {
  display: block;
}

.home {
  color: $secondary-color;
  // @extend %flex-align;
  @include flex-align(center, center);
  flex-direction: column;

  .character__list{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 2rem;
  }

  h1 {
    color: $primary-color;
  }

  &__content {
    min-width: 900px;
  }

  &__field {
    margin-bottom: 2rem;
    padding: 10px;
    display: flex;
    flex-direction: column;

    label {
      font-size: 2rem;
      font-weight: bold;
      color: $primary-color;
      text-align: left;
      padding-bottom: 10px;
    }

    input,
    textarea {
      border: 1px solid $secondary-color;
      padding: 1.5rem;
      outline: none;
      background-color: lighten($filled-bg, 1%);
      font-size: 1.3rem;
      word-wrap: break-word;
    }
    > * {
      display: block;
    }
  }

  .btn-primary {
    background-color: $secondary-color;
    padding: 16px 48px;
    border-radius: 10px;
    font-size: 1.3rem;
    margin-bottom: 2rem;
    border-width: 1px;
    border-style: solid;
    border-color: transparent;
    color: #fff;
    transition-property: background-color, color;
    transition-duration: 0.3s;
    transition-timing-function: ease-in;
    cursor: pointer;

    &:hover {
      background-color: darken($secondary-color, 3%);
    }
  }

  // Card List
  &__card-list {
    @include flex-align(space-around, center);
    grid-gap: 1.3rem;
    // justify-content: space-around
  }

  &__card-item {
    max-width: 230px;
    padding: 10px;
    height: auto;
    word-wrap: break-word;
    box-shadow: 0 0 5px 1px #333;
    position: relative;
  }

  &__close-btn {
    color: $red-color;
    width: 15px;
    height: auto;
    position: absolute;
    top: 5px;
    right: 5px;
    font-size: 1.3rem;
    transition: all 0.3s ease-in-out;
    cursor: pointer;

    &:hover {
      color: lighten($red-color, 30%);
    }
  }
}
</style>
