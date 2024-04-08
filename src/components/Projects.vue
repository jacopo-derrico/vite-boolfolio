<script>
import axios from 'axios';

export default{
  name: 'Projects',
  data(){
    return{
      projectArray: [],
    }
  },
  methods: {
    getProjects() {
      axios.get( 'http://127.0.0.1:8000/api/projects' )
        .then(res=>{
          console.log(res.data.projects)
          this.projectArray = res.data.projects
        })
    }
  },
  mounted() {
    this.getProjects()
  },
}
</script>

<template>
  <main>
    <h1>Projects</h1>

    <ul>
      <li v-for="(proj, index) in projectArray" :key="proj.id">
        {{ proj.title }}
      </li>
    </ul>
  </main>
</template>

<style scoped>

</style>
