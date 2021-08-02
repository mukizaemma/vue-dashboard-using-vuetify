<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="800px">
      <template v-slot:activator="{ on }">
        <v-btn outlined color="teal lighten-3" dark v-on="on"
          >Add New Project
        </v-btn>
      </template>

      <v-card>
        <v-card-title>
          <span class="headline">New Project</span>
        </v-card-title>

        <v-form class="px-3" ref="form">
          <v-card-text>
            <v-text-field
              label="Project Name"
              v-model="title"
              preprend-icon="folder"
              rules="inputRules"
            ></v-text-field>
            <v-text-field
              label="Location"
              v-model="text"
              preprend-icon="folder"
              :rules="inputRules"
            ></v-text-field>
            <v-textarea
              label="Description"
              v-model="content"
              preprend-icon="edit"
              :rules="inputRules"
            ></v-textarea>
            <v-col cols="12" sm="6">
              <v-menu
                ref="menu"
                v-model="menu"
                :close-on-content-click="false"
                :return-value.sync="dates"
                transition="scale-transition"
                offset-y
                min-width="auto"
              >
                <template v-slot:activator="{ on, attrs }">
                  <v-text-field
                    v-model="dates"
                    label="Date"
                    prepend-icon="mdi-calendar"
                    readonly
                    v-bind="attrs"
                    v-on="on"
                  ></v-text-field>
                </template>
                <v-date-picker v-model="dates" multiple no-title scrollable>
                  <v-spacer></v-spacer>
                  <v-btn text color="primary" @click="menu = false">
                    Cancel
                  </v-btn>
                  <v-btn text color="primary" @click="$refs.menu.save(dates)">
                    OK
                  </v-btn>
                </v-date-picker>
              </v-menu>
            </v-col>
          </v-card-text>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="red darken-1" text @click="dialog = false"
              >Close</v-btn
            >
            <v-btn color="blue darken-4" text outlined @click="submit"
              >Save</v-btn
            >
          </v-card-actions>
        </v-form>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  data: (vm) => ({
    dialog: false,
    title: "",
    content: "",
    date: new Date().toDateString().substr(0, 10),
    dateFormatted: vm.formatDate(new Date().toISOString().substr(0, 10)),
    menu: false,
    inputRules: [(v) => v.lenght >= 3 || "Minimun is 3 Characters"],
  }),
  methods: {
    formatDate(date) {
      if (!date) return null;
      const [year, month, day] = date.split("-");
      return "${year}/${month}/${day}";
    },
    computed: {
      computedDateFormatted() {
        return this.formatDate(this.date);
      },
    },
    watch: {
      date() {
        this.dateFormtted = this.formatDate(this.date);
      },
    },
  },
};
</script>

<style></style>
