<script>
import { RouterLink } from 'vue-router';

export default {
  name: "ProjectCard",
  components: {
    RouterLink
 },
  props: [
    "propElement"
    ],
};
</script>

<template>
    <div class="col-4">
        <div class="card text-start p-3 mb-3 ">
          <figure v-show="propElement.img">
            <img
              class="card-img-top"
              :src="propElement.img"
            />
          </figure>
          <div class="card-body">
            <h4 class="card-title"><RouterLink :to="{name: 'single-project', params: {slug: propElement.slug}}">{{ propElement.title }}</RouterLink></h4>
            <ul>
              <li>
                slug: <strong>{{ propElement.slug }}</strong>
              </li>
              <li v-if="propElement.category">
                category:
                <strong>{{ propElement.category.name }}</strong>
              </li>
              <li>
                tags:
                <span
                  v-for="(element, index) in propElement.tags"
                  class="badge rounded-pill text-bg-primary me-1"
                  >{{ element.name }}</span
                >
              </li>
            </ul>
            <p class="card-text">{{ propElement.description }}</p>
          </div>
        </div>
    </div>
</template>

<style scoped>

</style>