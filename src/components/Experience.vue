<template>
  <div id="experience">
    <section class="section">
      <div class="container has-text-centered">
        <h1 class="title pt-1-half">
          Experience
        </h1>
        <p class="subtitle is-italic">
          What I Contribute
        </p>
      </div>
    </section>

    <div class="columns is-centered pb-4 pt-1-half">
      <div class="column is-four-fifths-tablet is-three-fifths-desktop">
        <div class="is-size-5 readability-fix">
          <h3 class="has-text-weight-bold is-size-4-tablet">Web Developer at California State University, Northridge</h3>
          <p class="has-text-weight-light">November 2015 - Present</p>
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
      margin-right: 10%;
      margin-left: 10%;
    }
  }
  .readability-fix {
    margin-right: 5%;
    margin-left: 5%;
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
