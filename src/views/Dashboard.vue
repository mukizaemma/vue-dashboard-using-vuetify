<template>
  <div>
    <h1 class="subheading grey--text">Dashboard</h1>
    <v-container>
      <v-layout raw warap>
        <v-flex sm6 sm12 md6 lg3>
          <v-card class="ma-3">
            <v-list-item>
              <v-list-item-avatar tile class="mt-n7">
                <v-sheet color="green" width="40" height="80">
                  <v-icon dark large m-auto>store</v-icon>
                </v-sheet>
              </v-list-item-avatar>
              <v-list-item-content>
                <div class=" overline text-right">Article</div>
                <v-list-item-title class="headline mb-1 text-right"
                  >52334345</v-list-item-title
                >
                <div><v-divider></v-divider></div>
              </v-list-item-content>
            </v-list-item>
            <v-card-actions>
              <v-icon text class="ma-2">person</v-icon>
              <div class="overline">Emma</div>
            </v-card-actions>
          </v-card>
        </v-flex>

        <v-flex sm6 sm12 md6 lg3>
          <v-card class="ma-3">
            <v-list-item>
              <v-list-item-avatar tile class="mt-n7">
                <v-sheet color="green" width="40" height="80">
                  <v-icon dark large m-auto>store</v-icon>
                </v-sheet>
              </v-list-item-avatar>
              <v-list-item-content>
                <div class=" overline text-right">Article</div>
                <v-list-item-title class="headline mb-1 text-right"
                  >52334345</v-list-item-title
                >
                <div><v-divider></v-divider></div>
              </v-list-item-content>
            </v-list-item>
            <v-card-actions>
              <v-icon text class="ma-2">person</v-icon>
              <div class="overline">Emma</div>
            </v-card-actions>
          </v-card>
        </v-flex>

        <v-flex sm6 sm12 md6 lg3>
          <v-card class="ma-3">
            <v-list-item>
              <v-list-item-avatar tile class="mt-n7">
                <v-sheet color="green" width="40" height="80">
                  <v-icon dark large m-auto>store</v-icon>
                </v-sheet>
              </v-list-item-avatar>
              <v-list-item-content>
                <div class=" overline text-right">Article</div>
                <v-list-item-title class="headline mb-1 text-right"
                  >52334345</v-list-item-title
                >
                <div><v-divider></v-divider></div>
              </v-list-item-content>
            </v-list-item>
            <v-card-actions>
              <v-icon text class="ma-2">person</v-icon>
              <div class="overline">Emma</div>
            </v-card-actions>
          </v-card>
        </v-flex>

        <v-flex sm6 sm12 md6 lg3>
          <v-card class="ma-3">
            <v-list-item>
              <v-list-item-avatar tile class="mt-n7">
                <v-sheet color="green" width="40" height="80">
                  <v-icon dark large m-auto>store</v-icon>
                </v-sheet>
              </v-list-item-avatar>
              <v-list-item-content>
                <div class=" overline text-right">Article</div>
                <v-list-item-title class="headline mb-1 text-right"
                  >52334345</v-list-item-title
                >
                <div><v-divider></v-divider></div>
              </v-list-item-content>
            </v-list-item>
            <v-card-actions>
              <v-icon text class="ma-2">person</v-icon>
              <div class="overline">Emma</div>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
      <v-layout row nowrap>
        <v-flex xs12 sm6 mb4 lg3 v-for="person in team" :key="person.name">
          <v-card class="text-center ma-3">
            <v-responsive class="pt-4">
              <v-avatar size="100" class="maroon lighten-2">
                <v-img :src="person.avator"></v-img>
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="subheading">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn outlined color="green">
                <v-icon small left>message</v-icon>
                <span>Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    team: [
      { name: "Emma", role: "Software Developer", avator: "/emma.jpg" },
      { name: "Brian", role: "Software Analyst", avator: "/avator.jpg" },
      { name: "Bajo", role: "Marketing Exective", avator: "/avator.jpg" },
      { name: "Mambo", role: "Acountant", avator: "/avator.jpg" },
    ],
  }),
};
</script>
