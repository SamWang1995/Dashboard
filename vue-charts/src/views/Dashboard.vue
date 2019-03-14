<template>
  <div class="dashboard">
      <h1 class="subheading grey--text">Dashboard</h1>

      <v-container class="my-5">

        <v-layout row class="mb-3">
          <v-tooltip top>
            <v-btn small flat color="grey" @click="sortBy('title')" slot="activator">
              <v-icon left small> folder </v-icon>
              <span class="caption text-lowercase">by project name</span>
            </v-btn>
            <span>Sort projects by project name</span>
          </v-tooltip>
            
          <v-tooltip top>
            <v-btn small flat color="grey" @click="sortBy('person')" slot="activator">
              <v-icon left small> person </v-icon>
              <span class="caption text-lowercase">by person</span>
            </v-btn>
            <span>Sort projects by person</span>
          </v-tooltip>
          
        </v-layout>

        <v-card flat v-for="project in projects" :key="project.title">
          <v-layout row wrap :class="`pa-3 project ${project.status}`">
            <v-flex xs12 md6>
              <div class="caption grey--text">title</div>
              <div>{{ project.title }}</div>
            </v-flex>
            <v-flex xs6 sm4 md2>
              <div class="caption grey--text">person</div>
              <div>{{ project.person }}</div>
            </v-flex>
            <v-flex xs6 sm4 md2>
              <div class="caption grey--text">due by</div>
              <div>{{ project.due }}</div>
            </v-flex>
            <v-flex xs2 sm4 md2>
              <div class="right">
                <v-chip small :class="`${project.status} white--text caption my-2`">{{project.status}}</v-chip>
              </div>
            </v-flex>
          </v-layout>
          <v-divider></v-divider>
        </v-card>
      </v-container>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        projects: [
          { title: 'Project A', person: 'Samuel Wang', due:'Jan 1st 2019', status:'Ongoing'},
          { title: 'Project C', person: 'Samuel Wang', due:'Jan 1st 2019', status:'Ongoing'},
          { title: 'Project B', person: 'Samuel Wang', due:'Jan 1st 2019', status:'Overdue'},
          { title: 'Project D', person: 'Sam Wang', due:'Jan 1st 2019', status:'Overdue'},
          { title: 'Project E', person: 'Sam Wang', due:'Jan 1st 2019', status:'Complete'},
          { title: 'Project F', person: 'Sam Wang', due:'Jan 1st 2019', status:'Complete'},
        ]
      }
    },
    methods:{
    sortBy(prop){
      this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
    }
  }
  }
  

</script>

<style>
.project.Complete{
  border-left: 4px solid #3cd1c2;
}
.project.Ongoing{
  border-left: 4px solid orange;
}
.project.Overdue{
  border-left: 4px solid tomato;
}
.v-chip.Complete{
  background: #3cd1c2;
}
.v-chip.Ongoing{
  background: orange;
}
.v-chip.Overdue{
  background: tomato;
}
</style>
