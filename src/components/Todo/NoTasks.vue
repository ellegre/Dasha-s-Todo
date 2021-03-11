<template>
  <div 
      class="no-tasks">
      <v-icon
      size="80"
      color="primary"
      >mdi-check
      </v-icon>
      <div class="text-h5 primary--text">No tasks!</div>
    </div>
</template>

<style lang="sass">
.no-tasks 
  position: absolute
  top: 50%
  left: 50%
  transform:  translate(-50%, -50%)
  opacity: 0.6

</style>