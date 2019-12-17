<template>
  <v-btn
    icon
    max-width="36"
    max-height="36"
    rounded 
    text>

      <v-icon
        color="white"
        dense
        size="20px"
        class="nav__icons">
        {{ navIcon }}
      </v-icon>
      
  </v-btn>
</template>

<script>
export default {
  props: {
    navIcon: String
  }
}
</script>

<style>

</style>