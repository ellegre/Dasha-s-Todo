<template>
  <v-snackbar
        v-model="$store.state.snackbar.show"
        shaped 
        color="teal lighten-4"
        elevation="24"
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
</style>