<template>
  <div id="home">
    <section id="home-section" class="section">
      <div class="container has-text-centered">
        <h1 class="title pt-1-half">
          Hello there!
        </h1>
        <p class="subtitle is-italic">
          Nice to meet you.
        </p>
      </div>
    </section>

    <div class="columns is-centered pb-4 pt-1-half">
      <div class="column is-four-fifths-tablet is-three-fifths-desktop">
        <p class="is-size-5 readability-fix">
          I'm Luis a <strong>Software Engineer</strong> from the
          <strong>Los Angeles</strong> area with <strong>{{ this.diff }} years</strong>
          of experience working as a <strong>Full Stack Web Developer</strong>
          who understands how to translate a <strong>client’s needs</strong>
          into a straightforward <strong>software design</strong> that applies
          standard <strong>code conventions</strong>,
          <strong>unit testing</strong>, and
          <strong>extensive documentation</strong>. I have a proven track
          record of <strong>designing</strong> and <strong>developing</strong>
          modern and <strong>responsive web applications</strong> as well as
          <strong>REST APIs</strong>. Additionally, I'm also an experienced
          <strong>team leader</strong> and <strong>mentor</strong>
          that understands <strong>software</strong> is built by a <strong>team</strong> of
          unique <strong>individuals</strong> striving to solve one
          <strong>goal</strong>.
        </p>
        <p class="is-size-5 has-text-centered pt-1-half readability-fix"> If you would like to
          know more about me or are interested in collaborating,
          feel free and <strong><a href="mailto:contact@luisjg.dev"
            rel="noopener noreferrer" target="_blank"
            aria-label="Send me an e-mail, let's talk."><u>send me an email</u></a></strong>.
        </p>
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
    margin-left: 5%;
    margin-right: 5%;
  }
</style>

<script>
export default {
  data () {
    return {
      now: new Date(),
      then: new Date('2016-02-14'),
      diff: null
    }
  },
  created () {
    this.diff = this.now.getFullYear() - this.then.getFullYear()
  }
}
</script>
