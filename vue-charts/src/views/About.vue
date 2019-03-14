<template>
  <div class="about">
    <h1 class="subheading grey--text">This is an about page</h1>
    <v-container class="my-5">
        <v-layout row wrap>
            <v-flex xs12 sm6 md4 lg3 v-for="project in projects" :key="project.title">
                <v-card flat>hello</v-card>
            </v-flex>
        </v-layout>
    </v-container>
  </div>
</template>
<script>

  export default {
      data(){
          return{
              projects: [
                  { title: 'Project Charts', description: 'VueJS + ChartJS'},
                  { title: 'Project Charts', description: 'VueJS + ChartJS'},
                  { title: 'Project Charts', description: 'VueJS + ChartJS'},
                  { title: 'Project Charts', description: 'VueJS + ChartJS'},
                  { title: 'Project Charts', description: 'VueJS + ChartJS'}
              ]
          }
      }
  }
</script>