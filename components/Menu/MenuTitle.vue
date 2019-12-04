<template>
  <v-list-item active-class="listActive">
    <v-list-item-icon>
      <v-icon small :color="menuIconColor">{{ menuIcon }}</v-icon>
    </v-list-item-icon>

    <v-list-item-action>
      <v-list-item-title>{{ menuTitle }}</v-list-item-title>
    </v-list-item-action>
  </v-list-item>
</template>

<script>
export default {
  props: {
    menuIconColor: String,
    menuIcon: String,
    menuTitle: String
  }
};
</script>

<style scoped>
.listActive {
  font-weight: bold;
  margin-left: 20px;
  transition: 0.25s;
}
</style>