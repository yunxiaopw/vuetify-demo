<template>
  <div class="project">
    <h1 class="subheading grey--text">Projects</h1>
    <v-container fluid
                 class="my-5">
      <v-expansion-panels>
        <v-expansion-panel v-for="(project,index) in myProjects"
                           :key="`${project.person+index}`">
          <v-expansion-panel-header>{{
            project.title
          }}</v-expansion-panel-header>
          <v-expansion-panel-content>
            <div class="grey--text">
              <div class="font-weight-bold">Due by {{ project.due }}</div>
              <div>{{ project.content }}</div>
            </div>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      projects: [
        {
          title: 'Design a new website',
          person: 'The Net Ninjia',
          due: '1ts Jan 2020',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta maiores veniam deserunt labore illo consectetur nisi expedita officiis. Ad, iure explicabo fugiat magni possimus quibusdam optio accusantium dolorum tenetur dolore.',
        },
        {
          title: 'Design a new',
          person: 'Chun Li',
          due: '1ts Jan 2020',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta maiores veniam deserunt labore illo consectetur nisi expedita officiis. Ad, iure explicabo fugiat magni possimus quibusdam optio accusantium dolorum tenetur dolore.',
        },
        {
          title: 'Design a ',
          person: 'Ryu',
          due: '1ts Jan 2020',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta maiores veniam deserunt labore illo consectetur nisi expedita officiis. Ad, iure explicabo fugiat magni possimus quibusdam optio accusantium dolorum tenetur dolore.',
        },
        {
          title: 'Design',
          person: 'Gouken',
          due: '1ts Jan 2020',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta maiores veniam deserunt labore illo consectetur nisi expedita officiis. Ad, iure explicabo fugiat magni possimus quibusdam optio accusantium dolorum tenetur dolore.',
        },
        {
          title: 'Design a new website ..again',
          person: 'The Net Ninjia',
          due: '1ts Jan 2020',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Dicta maiores veniam deserunt labore illo consectetur nisi expedita officiis. Ad, iure explicabo fugiat magni possimus quibusdam optio accusantium dolorum tenetur dolore.',
        },
      ],
    }
  },
  computed: {
    myProjects () {
      return this.projects.filter(project => {
        return project.person === 'The Net Ninjia'
      })
    }
  }
}
</script>
