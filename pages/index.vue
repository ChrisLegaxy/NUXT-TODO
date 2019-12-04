<template>
  <div>
    <MainNavBar />

    <v-container>
      <v-row justify="center">
        <v-col cols="3">
          <MainMenu />
        </v-col>

        <v-col cols="8">
          <v-card>
            <v-subheader>
              <span>My Day</span>

              <v-btn
                icon
                rai
                absolute
                right
                color="white"
                style="background-color: #41B883"
                @click="dialog = true"
              >
                <v-icon>mdi-plus</v-icon>
              </v-btn>

              <v-dialog v-model="dialog" width="500">
                <v-card>
                  <v-card-title
                    class="font-weight-black white--text"
                    style="font-size: 24px; background-color: #41B883"
                    primary-title
                  >Add Task</v-card-title>

                  <v-card-text>
                    <v-container>
                      <v-row>
                        <v-col cols="12">
                          <v-text-field label="Task Name" color="teal" required></v-text-field>
                        </v-col>
                        <v-col cols="12">
                          <v-textarea color="teal">
                            <template v-slot:label>
                              <div>Task Description</div>
                            </template>
                          </v-textarea>
                        </v-col>
                      </v-row>
                    </v-container>
                  </v-card-text>

                  <v-divider></v-divider>

                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="error" text @click="dialog = false">Cancel</v-btn>
                    <v-btn color="primary" text @click="dialog = false">Save</v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-subheader>

            <v-list rounded>
              <v-list-item-group>
                <div class="d-flex flex-row">
                  <v-checkbox class="mx-5" style="vertical-align: text-bottom"></v-checkbox>
                  <v-list-item class="mb-2">
                    <v-list-item-content>
                      <v-list-item-title>Do something</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </div>
              </v-list-item-group>
            </v-list>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import MainNavBar from "~/layouts/Navigation Bar/MainNavBar";
import MainMenu from "~/layouts/Menu/MainMenu";

export default {
  data() {
    return {
      dialog: false
    };
  },
  components: {
    MainNavBar,
    MainMenu
  },
  methods: {}
};
</script>

<style scoped>
</style>
