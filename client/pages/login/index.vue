<template>
  <v-container style="margin: auto;">
    <v-row align="center" justify="center">
      <v-card min-width="550px" raised shaped>
        <v-card-title
          class="font-weight-black white--text"
          style="font-size: 24px; background-color: #41B883"
          primary-title
        >Nuxt TODO</v-card-title>
        <div class="form-container">
          <v-form @submit="login()">
            <v-text-field type="text" placeholder="Username"></v-text-field>
            <v-text-field type="password" placeholder="Password"></v-text-field>
            <v-row style="margin-bottom: 15px;">
              <v-col>
                <v-btn color="primary">Login</v-btn>
              </v-col>
              <v-col class="text-right">
                <v-btn color="error">Forget Password</v-btn>
              </v-col>
            </v-row>
          </v-form>
        </div>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
import axios from 'axios';

export default {
  layout: 'loginLayout'
};
</script>
<style>
.form-container {
  margin: 0 20px;
}
</style>