<script>
export default {
  name: "ProjectCard",
  props: [
    "propElement"
    ],
};
</script>

<template>
    <div class="col-4">
        <div class="card text-start p-3">
          <figure v-show="propElement.img">
            <img
              class="card-img-top"
              :src="propElement.img"
            />
          </figure>
          <div class="card-body">
            <h4 class="card-title">{{ propElement.title }}</h4>
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

h1 {
  color: $font-color-second;
  @include main-font-start;
}

li {
  list-style-type: disc;
}

.project-container {
  height: 450px;

  .project-card {
    height: 100%;
    overflow: auto;
  }
}

ol,
ul {
  padding-left: 1rem;
}
</style>