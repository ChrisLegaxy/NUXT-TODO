<template>
  <v-app-bar flat color="#41B883">
    <v-container>
      <v-row align="center" justify="center">
        <v-col cols="4" sm="5" lg="4">
          <NavTitle />
        </v-col>

        <v-col cols="1" sm="1" lg="4" />

        <v-col class="text-right" sm="6" lg="3">
          <NavIcon class="mx-3" v-for="icon in fasIcon" :key="icon.id" :navIcon="icon"></NavIcon>
        </v-col>
      </v-row>
    </v-container>
  </v-app-bar>
</template>

<script>
import NavTitle from "@/components/Navigation Bar/NavTitle";
import NavIcon from "@/components/Navigation Bar/NavIcon";

export default {
  components: {
    NavTitle,
    NavIcon
  },
  data() {
    return {
      fasIcon: ["fas fa-search", "fas fa-bell", "fas fa-user"]
    };
  }
};
</script>

<style>
</style>
