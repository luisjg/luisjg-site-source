<template>
  <div id="portfolio">
    <section id="portfolio-section" class="section">
      <div class="container has-text-centered">
        <h1 class="title pt-1-half">
          Portfolio
        </h1>
        <p class="subtitle is-italic">
          What We Built
        </p>
      </div>
    </section>

    <div class="columns is-centered pt-1-half">
      <div  v-for="(item, value) in firstHalfOfProjects" :key="value" class="column is-one-quarter-tablet is-one-fifth-desktop">
        <figure class="image">
          <a @click.prevent="modalAction" href="#"><img :data-id="item[0]" :src="item[1].image" :alt="item[1].title + ' App Image'"></a>
        </figure>
        <p class="has-text-centered title is-size-4 pt-1-half"><u><a @click.prevent="modalAction" :data-id="item[0]" href="#" class="app-links">{{ item[1].title }}</a></u></p>
        <div class="has-text-centered is-size-5" v-html="item[1].description"></div>
      </div>
    </div>

    <div class="columns is-centered pb-4">
      <div v-for="(item, value) in secondHalfOfProjects" :key="value" class="column is-one-quarter-tablet is-one-fifth-desktop">
        <figure class="image">
          <a @click.prevent="modalAction" href="#"><img :data-id="item[0]" :src="item[1].image" :alt="item[1].title + ' App Image'"></a>
        </figure>
        <p class="has-text-centered title is-size-4 pt-1-half"><u><a @click.prevent="modalAction" :data-id="item[0]" href="#" class="app-links">{{ item[1].title }}</a></u></p>
        <div class="has-text-centered is-size-5" v-html="item[1].description"></div>
      </div>
    </div>

    <modal v-if="status" :class="{'is-active': status}" @disable="updateModal" :modalAttrs="modalAttrs"></modal>
  </div>
</template>

<script>
  import { mapGetters } from 'vuex'
  export default {
    data () {
      return {
        status: false,
        modalAttrs: null
      }
    },
    methods: {
      modalAction: function (event) {
        this.modalAttrs = this.workData[event.target.dataset.id]
        this.modalAttrs.id = event.target.dataset.id
        document.documentElement.classList.add('is-clipped')
        this.updateModal()
      },
      updateModal: function () {
        this.status = !this.status
      }
    },
    components: {
      'modal': () => import('@/components/Modal')
    },
    computed: {
      ...mapGetters([
        'workData'
      ]),
      firstHalfOfProjects: function () {
        return Object.entries(this.workData).slice(0, (Object.keys(this.workData).length / 2))
      },
      secondHalfOfProjects: function () {
        return Object.entries(this.workData).slice((Object.keys(this.workData).length / 2), Object.keys(this.workData).length)
      }
    }
  }
</script>
