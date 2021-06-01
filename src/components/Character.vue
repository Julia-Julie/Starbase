<template>
  <div class="character" @click="getAnotherOne">

    <h3 class="character__name">{{character.name}}</h3>
    <div class="character__height">{{character.height}}cm</div>
    <div class="character__mass">{{character.mass}}kg</div>
    <div class="character__hair-color">{{character.hair-color}}</div>
    <div class="character__eye-color">{{character.eye-color}}</div>
    <div class="character__gender">{{character.gender}}</div>


    <!-- <pre>
      {{ character }}
    </pre> -->
  </div>
</template>

<script>
export default {
  props: ["id"],

  data() {
    return {
      character: {},
    };
  },

  methods: {
    getCharachers(id) {
      fetch(`https://swapi.dev/api/people/${id}`, {
        method: "Get",
      })
        .then((response) => response.json())
        .then((json) => (this.character = json));
    },

    getAnotherOne() {
      let random_id = Math.floor(Math.random() * 80 + 1);
      this.getCharachers(random_id);
    },
  },

  created() {
    this.getCharachers(this.id);
  },
};
</script>

<style scoped lang="scss">
  $green-color: rgb(29, 107, 81);

  .character{
     border: 2px solid $green-color;
     cursor: pointer;
     transition: all .6s ease-in-out;

     &:hover{
        border-color: lighten($green-color, 30%);
        box-shadow: 0px 0px 10px 1px $green-color;
        // transform: rotateY(-180deg);
     }

    > * {
      border-bottom: 1px dashed violet;
      padding: 10px;
      margin-bottom: 1rem;

      &:last-child{
        border-bottom: none;
      }
    }

    &__name{
      font-size: 1.5rem;
      font-style: italic;
      font-weight: 700;
    }
  }

</style>
