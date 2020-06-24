<template>
  <v-dialog persistent
            v-model="dialog"
            max-width="600px">
    <template v-slot:activator="{ on, attrs }">
      <v-btn color="success"
             dark
             v-bind="attrs"
             v-on="on">
        Add a new project
      </v-btn>
    </template>
    <v-card>
      <v-card-title class="headline grey lighten-2"
                    primary-title>
        <h2>Add a New Project</h2>
      </v-card-title>

      <v-card-text>
        <v-form class="px-3">
          <v-text-field label="Title"
                        v-model="title"
                        prepend-icon="folder"></v-text-field>
          <v-textarea label="Information"
                      v-model="content"
                      prepend-icon="edit"></v-textarea>

          <v-row justify="space-around">
            <v-date-picker v-model="due"
                           locale="zh-cn"></v-date-picker>
          </v-row>
        </v-form>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="primary"
               text
               @click="submit">
          Add Project
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>

</template>

<script>
export default {
  data () {
    return {
      dialog: false,
      title: '',
      content: '',
      due: new Date().toISOString().substr(0, 10)
    }
  },
  methods: {
    submit () {
      console.log(this.title, this.content)
      console.log(this.due)
      this.dialog = false
    }
  }
};
</script>
<style scoped>
</style>