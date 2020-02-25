<template>
  <div>
    <b-table striped hover :items="dogs">
      <template v-slot:cell(name)="data">
        <router-link :to="`/pets/dogs/${data.index}`">{{ data.value }}</router-link>
      </template>
    </b-table>
  </div>
</template>

<script>
import { mapState } from "vuex"
export default {
  computed: {
    ...mapState(["dogs"]),
  },
}
</script>

<style lang="scss" scoped></style>
