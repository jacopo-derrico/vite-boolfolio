<script>
import { RouterLink, RouterView } from 'vue-router';
import Projects from './components/Projects.vue'

export default {
  components: {
    Projects,
  }
}
</script>

<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
      <div class="col-md-10 mx-auto d-flex ">
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <RouterLink :to="{name: 'home'}" class="nav-link">Home</RouterLink>
            </li>
            <li class="nav-item">
              <RouterLink :to="{name: 'projects'}" class="nav-link">Projects</RouterLink>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </nav>
  <main class="container-fluid">
    <div class="col-md-10 mx-auto">
      <RouterView></RouterView>
    </div>
  </main>
</template>

<style scoped>
</style>
