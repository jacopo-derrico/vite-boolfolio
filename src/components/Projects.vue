<script>
import axios from 'axios';
import ProjectCard from './ProjectCard.vue';

export default{
  components:{
        ProjectCard
    },
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
    <div class="container-fluid">
      <div class="row">
        <ProjectCard
            v-for="(proj, index) in projectArray"
            :key="proj.id"
            :propElement="proj"
          />
      </div>
    </div>
</template>

<style scoped>

</style>
