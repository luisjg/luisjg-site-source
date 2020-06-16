<template>
  <div id="experience">
    <section class="section">
      <div class="container has-text-centered">
        <h1 class="title">
          Experience
        </h1>
        <p class="subtitle">
          What I Contribute
        </p>
      </div>
    </section>

    <div class="columns is-centered is-mobile pb-4">
      <div class="column is-half">
        <div class="is-size-5 readability-fix">
          <h3 class="has-text-weight-bold">Web Developer at California State University, Northridge</h3>
          <p>November 2015 - Present</p>
          <ul>
            <li class="icons list-element" v-for="(item, value) in experienceData" :key="value"><span>{{ item }}</span></li>
          </ul>
        </div>
      </div>
    </div>

  </div>
</template>

<style scoped>
  @media screen and (min-width: 1024px) {
    .readability-fix {
      width: 68ch;
    }
  }
  .is-size-4-desktop p {
    padding-top: 0.5rem;
  }
  li span {
    color: #4a4a4a;
  }
  li {
    list-style: square;
    margin-left: 1.20rem;
    padding-left: 1rem;
    margin-top: .5rem;
    color: #6d9f71;
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
