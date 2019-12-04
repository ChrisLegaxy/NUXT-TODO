<template>
  <v-app style="background-color: #fafafa;">
    <nuxt />
  </v-app>
</template>

<style>
@media only screen and (min-width: 1200px) {
  html {
    height: 80vh;
    overflow: auto;
  }
}

/* width */
::-webkit-scrollbar {
  width: 5px;
}

/* Track */
::-webkit-scrollbar-track {
  /* box-shadow: inset 0 0 5px grey;  */
  border-radius: 10px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #41b883;
  border-radius: 10px;
}

/* Handle on hover */
/* ::-webkit-scrollbar-thumb:hover {
  background: #41B883; 
} */
</style>
