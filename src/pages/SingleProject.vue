<script>
import axios from 'axios';

export default{
  name: 'SingleProject',
  data(){
    return{
      project: [],
    }
  },
  methods: {
    getSingleProject() {
      axios.get( `http://127.0.0.1:8000/api/projects/${this.$route.params.slug}` )
        .then(res=>{
          console.log(res.data.project)
          console.log(`http://127.0.0.1:8000/api/projects/${this.$route.params.slug}`)
          if (res.data.success) {
            this.project = res.data.project
          } else {
            console.log('error')
          }
        })
    }
  },
  mounted() {
    this.getSingleProject()
  },
}
</script>

<template>
    <div class="container-fluid">
      <div class="row">
        <h1>{{project?.title}}</h1>
        <ul>
              <li>
                slug: <strong>{{ project.slug }}</strong>
              </li>
              <li v-if="project.category">
                category:
                <strong>{{ project.category.name }}</strong>
              </li>
              <li>
                tags:
                <span
                  v-for="(element, index) in project.tags"
                  class="badge rounded-pill text-bg-primary me-1"
                  >{{ element.name }}</span
                >
              </li>
            </ul>
            <p class="card-text">{{ project.description }}</p>
      </div>
    </div>
</template>

<style scoped>

</style>
