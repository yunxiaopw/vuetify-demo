<template>
  <div class="Team">
    <h1 class="subheading grey--text">Team</h1>
    <v-container class="my-5">
      <v-row wrap>
        <v-col xs="12" sm="6" md="4" lg="3" v-for="person in team" :key="person.name">
          <v-card flat class="text-center ma-3">
            <v-responsive class="pt-4">
              <v-avatar size="100" class="grey lighten-2">
                <img :src="person.avatar">
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="subheading">{{person.name}}</div>
              <div class="grey--text">{{person.role}}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn text color="grey">
                <v-icon small left>message</v-icon>
                <span>message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      team: [
        { name: 'The net ninjia', role:'web developer', avatar:'/avatar-1.jpg'},
        { name: 'The net ninjia2', role:'web developer', avatar:'/avatar-1.jpg'},
        { name: 'The net ninjia3', role:'web developer', avatar:'/avatar-1.jpg'},
        { name: 'The net ninjia4', role:'web developer', avatar:'/avatar-1.jpg'},
        { name: 'The net ninjia5', role:'web developer', avatar:'/avatar-1.jpg'}
      ]
    }
  }
};
</script>
<style scoped>
.Team {
  background-color: #f5f5f5;
}
</style>