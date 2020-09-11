<template>
  <div id="experience">
    <section class="section">
      <div class="container has-text-centered">
        <h1 class="title pt-1-half">
          Skills
        </h1>
        <p class="subtitle is-italic">
          Tools I Know
        </p>
      </div>
    </section>

    <div class="columns is-centered pt-1-half">
      <div class="column is-one-quarter-tablet is-one-fifth-desktop">
        <div class="has-text-centered">
          <i class="fad fa-7x fa-laptop-code russian-green" aria-hidden="true"></i>
          <p class="title is-size-4 pt-1-half">Back End</p>
          <p class="is-size-5">
            PHP, Laravel, Lumen, REST APIs
          </p>
        </div>
      </div>
      <div class="column is-one-quarter-tablet is-one-fifth-desktop">
        <div class="has-text-centered padded--top__mobile">
          <i class="fad fa-7x fa-browser russian-green" aria-hidden="true"></i>
          <p class="title is-size-4 pt-1-half">Front End</p>
          <p class="is-size-5">
            HTML, CSS, JQuery, Vue.js, Socket.io
          </p>
        </div>
      </div>
      <div class="column is-one-quarter-tablet is-one-fifth-desktop">
        <div class="has-text-centered padded--top__mobile">
          <i class="fad fa-7x fa-conveyor-belt-alt russian-green" aria-hidden="true"></i>
          <p class="title is-size-4 pt-1-half">CI/CD</p>
          <p class="is-size-5">
            Travis CI, GitHub Actions
          </p>
        </div>
      </div>
    </div>

    <div class="columns is-centered pb-4">
      <div class="column is-one-quarter-tablet is-one-fifth-desktop">
        <div class="has-text-centered padded--top">
          <i class="fad fa-7x fa-database russian-green" aria-hidden="true"></i>
          <p class="title is-size-4 pt-1-half">Database</p>
          <p class="is-size-5">
            MongoDB, MySQL, Redis
          </p>
        </div>
      </div>
      <div class="column is-one-quarter-tablet is-one-fifth-desktop">
        <div class="has-text-centered padded--top">
          <i class="fad fa-7x fa-code-branch russian-green" aria-hidden="true"></i>
          <p class="title is-size-4 pt-1-half">Version Control</p>
          <p class="is-size-5">
            Git, GitHub
          </p>
        </div>
      </div>
      <div class="column is-one-quarter-tablet is-one-fifth-desktop">
        <div class="has-text-centered padded--top">
          <i class="fad fa-7x fa-server russian-green" aria-hidden="true"></i>
          <p class="title is-size-4 pt-1-half">DevOps</p>
          <p class="is-size-5">
            Docker, Ubuntu, Kubernetes
          </p>
        </div>
      </div>
    </div>

  </div>
</template>

<style scoped>
  .padded--top {
    padding-top: 1.5rem;
  }
  @media screen and (max-width: 768px) {
    .padded--top__mobile {
      padding-top: 1.5rem;
    }
  }
</style>

<script>
  import { mapGetters } from 'vuex'
  export default {
    computed: {
      ...mapGetters([
        'experienceData'
      ])
    }
  }
</script>
