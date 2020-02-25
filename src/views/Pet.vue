<template>
  <div>
    <h1>{{ animal.name }} ({{ $route.params.species}})</h1>
    <p>{{ animal.age }} years old</p>
    <p>Breed {{ animal.breed }}</p>
  </div>
</template>

<script>
import { mapState } from "vuex"

export default {
  computed: {
    ...mapState(["cats", "dogs"]),
  },
  data() {
    return {
      animal: {},
    }
  },
  mounted() {
    const animalType = this.$route.params.species
    const id = this.$route.params.id
    const animal = this[animalType][id]
    this.animal = animal
  },
}
</script>

<style lang="scss" scoped></style>
