<template>
  <div class="projects">
    <h1 class="subheading grey--text">This is a project page</h1>
    <v-container class="my-5">
      <v-container class="my-5">
        <v-layout row wrap>
            <v-flex xs12 sm6 md4 lg3 v-for="project in projects" :key="project.title">
                <v-card flat class="text-xs-center ma-3">
                  <v-responsive class="pt-4">
                    <v-avatar size="100" class="grey lighten-2">
                      <img :src="project.pic">
                    </v-avatar>
                  </v-responsive>
                  <v-card-text>
                    <div class="subheading">{{project.title}}</div>
                    <div class="grey--text">{{project.description}}</div>
                    <v-btn flat color="grey">
                      <v-icon large class="center"> folder </v-icon>
                    </v-btn>
                  </v-card-text>
                  <v-card-actions>
                    

                  </v-card-actions>
                </v-card>
            </v-flex>
        </v-layout>
    </v-container>
      </v-container>
  </div>
</template>
<script>

  export default {
          data(){
          return{
              projects: [
                  { title: 'Project Charts', description: 'VueJS + ChartJS', pic: '/vuelogo.png'},
                  { title: 'Project Charts', description: 'VueJS + ChartJS', pic: '/vuelogo.png'},
                  { title: 'Project Charts', description: 'VueJS + ChartJS', pic: '/vuelogo.png'},
                  { title: 'Project Charts', description: 'VueJS + ChartJS', pic: '/vuelogo.png'},
                  { title: 'Project Charts', description: 'VueJS + ChartJS', pic: '/vuelogo.png'}
              ]
          }
      }
  }
</script>