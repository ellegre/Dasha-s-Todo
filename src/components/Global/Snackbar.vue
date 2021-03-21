<template>
  <v-snackbar
    v-model="$store.state.snackbar.show"
    flat
    light
    color="grey lighten-4"
    elevation="4"
  >
    {{ $store.state.snackbar.text }}

    <template v-slot:action="{ attrs }">
      <v-btn
        text
        v-bind="attrs"
        @click="$store.commit('hideSnackbar')"
      >
        Close
      </v-btn>
    </template>
  </v-snackbar>  
</template>

<script>
export default {

}
</script>

<style lang="sass">
  div.v-snack:not(.v-snack--absolute) 
    height: 100%
  .v-snack__wrapper 
    min-width: 300px !important
    .v-snack__content
      font-size: 1.1rem
      color: #0D4D52 
</style>