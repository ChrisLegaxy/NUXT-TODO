<template>
  <div>
    <v-list color="#fafafa" rounded>
      <v-list-item-group mandatory>
        <!-- Top Menu -->
        <MenuTitle
          v-for="menu in menus"
          :key="menu.key"
          :menuIconColor="menu.color"
          :menuIcon="menu.icon"
          :menuTitle="menu.title"
        />

        <v-divider class="mt-3" />

        <!-- Task Menu -->
        <v-subheader>Task List</v-subheader>

        <div class="overflow-y-auto" style="max-height: 175px" v-if="projectMenus.length > 0">
          <MenuTitle
            v-for="menu in projectMenus"
            :key="menu.key"
            :menuIconColor="menu.color"
            :menuIcon="menu.icon"
            :menuTitle="menu.title"
          />
        </div>

        <!-- Add List Menu with Dialog-->
        <div @click="dialog = true">
          <MenuTitle menuIconColor="teal" menuIcon="fas fa-plus" menuTitle="Add List" class="my-4" />
        </div>

        <!-- Dialog -->
        <v-dialog v-model="dialog" width="500">
          <v-card>
            <v-card-title
              class="font-weight-black white--text"
              style="font-size: 24px; background-color: #41B883"
              primary-title
            >Add List</v-card-title>

            <v-card-text>
              <v-container>
                <v-row>
                  <v-col class="d-flex flex-row" cols="12">
                    <v-text-field
                      v-model="newTaskTitle.title"
                      label="Task List Title"
                      color="teal"
                      class="mr-3"
                      required
                    />

                    <v-select
                      :items="colorList"
                      label="Color"
                      v-model="selectedColor"
                      item-text="name"
                      item-value="color"
                      return-object
                      class="ml-3"
                    >
                      <v-icon slot="append" :color="selectedColor.color">mdi-circle</v-icon>
                    </v-select>
                  </v-col>
                </v-row>
              </v-container>
            </v-card-text>

            <v-divider></v-divider>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="error" text @click="dialog = false">Cancel</v-btn>
              <v-btn color="primary" text @click="saveTask">Save</v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>

        <v-divider class="mt-3 mb-3" />

        <!-- Bottom Menu -->
        <MenuTitle
          v-for="menu in bottomMenus"
          :key="menu.key"
          :menuIconColor="menu.color"
          :menuIcon="menu.icon"
          :menuTitle="menu.title"
        />
      </v-list-item-group>
    </v-list>
  </div>
</template>

<script>
import MenuTitle from "@/components/Menu/MenuTitle";
import MenuDialog from "@/components/Menu/MenuTitle";

export default {
  components: {
    MenuTitle,
    MenuDialog
  },
  data() {
    return {
      colorList: [
        {
          name: "Blue",
          color: "blue"
        },
        {
          name: "Red",
          color: "red"
        },
        {
          name: "Orange",
          color: "orange"
        }
      ],
      selectedColor: {
        name: "Blue",
        color: "blue"
      },
      newTaskTitle: {
        color: "",
        icon: "fas fa-circle",
        title: ""
      },
      menus: [
        {
          color: "blue",
          icon: "fas fa-certificate",
          title: "My Day"
        },
        {
          color: "orange",
          icon: "fas fa-star",
          title: "Important"
        },
        {
          color: "green",
          icon: "fas fa-list",
          title: "Task"
        }
      ],
      projectMenus: [
        {
          color: "orange",
          icon: "fas fa-circle",
          title: "Create Website"
        },
        {
          color: "blue",
          icon: "fas fa-circle",
          title: "Derk24"
        }
      ],
      bottomMenus: [
        {
          color: "green",
          icon: "fas fa-check",
          title: "Completed"
        },
        {
          color: "blue-grey darken-4-gray",
          icon: "fas fa-trash",
          title: "Trash"
        }
      ],
      dialog: false
    };
  },
  methods: {
    saveTask() {
      this.projectMenus.push({
        color: this.selectedColor.color,
        icon: "fas fa-circle",
        title: this.newTaskTitle.title
      });
      this.newTaskTitle.title = "";
      this.dialog = false;
    },
    showAddTaskDialog() {
      this.$emit("showAddTaskDialog", true);
    }
  }
};
</script>

<style scoped>
.headline {
  background-color: #41b883;
  color: white;
}
</style>
