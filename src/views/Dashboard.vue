<template>
  <div class="dashboard">
    <h1 class="subheading grey--text">Dashboard</h1>
    <v-container class="my-5">
      <v-row class="mb-3">
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
              <v-btn small text color="grey" @click="sortBy('title')"  v-bind="attrs" v-on="on">
                <v-icon left small>folder</v-icon>
                <span class="caption text-lowercase">By project name</span>
              </v-btn>
          </template>
         <span>Sort projects by project name</span>
        </v-tooltip>
        <v-tooltip top>
          <template v-slot:activator="{ on, attrs }">
            <v-btn small text color="grey" @click="sortBy('person')" v-bind="attrs" v-on="on">
          <v-icon left small>person</v-icon>
          <span class="caption text-lowercase">By person</span>
        </v-btn>
        </template>
         <span>Sort projects by person</span>
        </v-tooltip>        
      </v-row>
      <v-card flat v-for="project in projects" :key="project.title">
        <v-row wrap :class="`pa-3 project ${project.status}`">
          <v-col xs="12" md="6">
            <div class="caption grey--text">Project title</div>
            <div>{{ project.title }}</div>
          </v-col>
          <v-col xs="6" sm="4" md="2">
            <div class="caption grey--text">Person</div>
            <div>{{ project.person }}</div>
          </v-col>
          <v-col xs="6" sm="4" md="2">
            <div class="caption grey--text">Due by</div>
            <div>{{ project.due }}</div>
          </v-col>
          <v-col xs="2" sm="4" md="2">
            <!-- <div class="caption grey--text">Status</div>
            <div>{{project.status}}</div> -->
            <div class="right">
              <v-chip small :class="`${project.status} white--text caption my-2`">{{ project.status }}</v-chip>
            </div>
          </v-col>
        </v-row>
        <v-divider></v-divider>
      </v-card>

      <!-- grid-1 -->
      <!-- <v-layout row wrap>
        <v-flex xs12 md6>
          <v-btn outlined block color="primary">1</v-btn>
        </v-flex>
        <v-flex xs4 md2>
          <v-btn outlined block class="primary">2</v-btn>
        </v-flex>
        <v-flex xs4 md2>
          <v-btn outlined block class="primary">2</v-btn>
        </v-flex>
        <v-flex xs4 md2>
          <v-btn outlined block class="primary">2</v-btn>
        </v-flex>
      </v-layout>

      <v-layout row wrap justify-space-around>
        <v-flex xs4 md3>
          <v-btn outlined block class="success">1</v-btn>
        </v-flex>
        <v-flex xs4 md3>
          <v-btn outlined block class="success">2</v-btn>
        </v-flex>
      </v-layout> -->
    </v-container>
  </div>
  <!-- <div class="dashboard"> -->
  <!-- <h1>HomePage</h1>
    <p class="red">Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis odio dolorum quis corporis ex saepe non quod, sequi eveniet ipsum consequatur eligendi quam, veritatis aliquam. Quidem tenetur et perspiciatis iusto!</p>
    <p class="red white--text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis odio dolorum quis corporis ex saepe non quod, sequi eveniet ipsum consequatur eligendi quam, veritatis aliquam. Quidem tenetur et perspiciatis iusto!</p>

    <p class="pink lighten-4 red--text text--darken-1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita accusamus possimus officiis similique optio qui ipsa, aspernatur facilis reiciendis neque architecto velit excepturi, debitis aliquam voluptatem nemo doloremque perspiciatis nam!</p>
    <h1 class="display-4">Massive Display</h1>
    <h1 class="display-1">smaller Display</h1>
    <p class="display-4">this is h label</p>
    <p class="highline">this is a highline</p>
    <p class="subheading">this is a subheading</p>
    <p class="caption font-weight-bold">this is a caption</p> -->
  <!-- 
    <h1>DashboardPage</h1>

    <v-btn class="pink white--text">clike me</v-btn>
    <v-btn dark
           color="pink">clike me</v-btn>
    <v-btn depressed
           color="pink">clike me</v-btn>
    <v-btn text
           color="pink">clike me</v-btn>

    <v-btn depressed
           class="pink white--text">
      <v-icon left>email</v-icon>
      <span>email me</span>
    </v-btn>

    <v-btn depressed
           small
           class="pink white--text">
      <v-icon left
              small>email</v-icon>
      <span>email me</span>
    </v-btn>

    <v-btn depressed
           large
           class="pink white--text">
      <v-icon left
              large>email</v-icon>
      <span>email me</span>
    </v-btn>

    <v-btn depressed
           fab
           small
           dark
           color="purple">
      <v-icon>favorite</v-icon>
    </v-btn>

    <h1>hidden</h1> -->
  <!-- <v-btn class="hidden-md-and-down">clike me</v-btn> -->
  <!-- <v-btn class="hidden-md-and-up">clike me</v-btn>
    <v-btn class="hidden-sm-only">clike me</v-btn>
  </div> -->
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: 'Aesign a new website',
          person: 'chun Li',
          due: 'jun 2020',
          status: 'completed',
        },
        {
          title: 'Design b new website',
          person: 'Monkey Li',
          due: 'jun 2020',
          status: 'ongoing',
        },
        {
          title: 'Design c new website',
          person: 'fire Li',
          due: 'jun 2020',
          status: 'overdue',
        },
        {
          title: 'Cat d new website',
          person: 'Dive Li',
          due: 'jun 2020',
          status: 'completed',
        },
      ],
    }
  },
  methods: {
    sortBy(prop){
      this.projects.sort((a,b)=>a[prop] < b[prop] ? -1 : 1)
    }
  }
}
</script>

<style>
.project.completed {
  border-left: 4px solid #3cd1c2;
}
.project.ongoing {
  border-left: 4px solid orange;
}
.project.overdue {
  border-left: 4px solid tomato;
}
.completed {
  color: #3cd1c2;
}
.ongoing {
  color: #ffaa2c;
}
.overdue {
  color: #f83e70;
}
</style>
