<template>
    <section class="hero is-medium is-light is-bold">

      <div class="hero-head">
        <nav class="navbar">
          <div class="container">
            <div class="navbar-brand">
              <router-link @click.native="closeHamburger()" :to="{name: 'home'}" class="home-logo navbar-item">
                <template v-if="hideNav">
<!--                  <img src="https://res.cloudinary.com/dfhliq7vp/image/upload/v1547432443/luisjg/profile.jpg" class="brand-image" alt="profile image">-->
<!--                  <span class="is-size-5 brand-text">luisjg.io</span>-->
                  <span class="is-size-5">luisjg.io</span>
                </template>
                <template v-else>
                  <span class="is-size-5">Return back to luisjg.io</span>
                </template>
              </router-link>
              <span @click="hamburgerToggle()" :class="{'is-active': isActive }" class="navbar-burger burger">
                <span></span>
                <span></span>
                <span></span>
              </span>
            </div>

            <div :class="{'is-active': isActive }" class="navbar-menu">
              <div class="navbar-end">
                <template v-if="hideNav">
                  <router-link @click.native="hamburgerToggle()" :to="{name: 'home'}" exact-active-class="is-active" class="navbar-item">
                    <span class="has-text-weight-bold">01</span>&nbsp;Home
                  </router-link>
                  <router-link @click.native="hamburgerToggle()" :to="{name: 'portfolio'}" active-class="is-active" class="navbar-item">
                    <span class="has-text-weight-bold">02</span>&nbsp;Portfolio
                  </router-link>
                  <router-link @click.native="hamburgerToggle()" :to="{name: 'experience'}" active-class="is-active" class="navbar-item">
                    <span class="has-text-weight-bold">03</span>&nbsp;Experience
                  </router-link>
                  <router-link @click.native="hamburgerToggle()" :to="{name: 'skills'}" active-class="is-active" class="navbar-item">
                    <span class="has-text-weight-bold">04</span>&nbsp;Skills
                  </router-link>
                  <router-link @click.native="hamburgerToggle()" :to="{name: 'blog'}" active-class="is-active" class="navbar-item">
                    <span class="has-text-weight-bold">05</span>&nbsp;Blog
                  </router-link>
                </template>
                <template v-else>
                  <router-link @click.native="hamburgerToggle()" :to="{name: 'blog'}" exact-active-class="is-active" class="navbar-item">
                    Posts
                  </router-link>
                </template>
              </div>
            </div>
          </div>
        </nav>
      </div>

      <div v-if="hideNav" class="hero-body">
        <div class="container has-text-centered">
          <figure class="image is-responsive">
            <img src="https://res.cloudinary.com/dfhliq7vp/image/upload/v1547432443/luisjg/profile.jpg" class="is-rounded" alt="profile image">
          </figure>
          <ul id="tag-lines" class="is-size-5">
            <li>
              <i class="russian-green fad fa-map-marker-alt" aria-hidden="true"></i> Los Angeles, CA
            </li>
            <li>
              <i class="russian-green fad fa-graduation-cap" aria-hidden="true"></i> Computer Science, BS
            </li>
            <li>
              <i class="russian-green fad fa-briefcase" aria-hidden="true"></i> Web Developer, CSUN IT
            </li>
          </ul>
        </div>
      </div>
    </section>
</template>

<style scoped>
  .is-rounded {
    -moz-box-shadow: 4px 4px 10px rgba(0,0,0, 0.5);
    -webkit-box-shadow: 4px 4px 10px rgba(0,0,0, 0.5);
    box-shadow: 4px 4px 10px rgba(0,0,0, 0.5);
  }
    #tag-lines {
    padding-top: .5rem;
  }
  .brand-image {
    padding-top: .025em;
    border-radius: 50%;
  }
  .brand-text {
    padding-left: .3em;
  }
  .image {
    margin: auto;
  }
  .image.is-responsive {
    height: 110px;
    width: 110px;
  }
  .hero.is-light.is-bold {
    background-image: none;
    background-color: #f7f8fa;
  }
  .hero.is-light .navbar-item {
    background-color: #f7f8fa;
    border-color: transparent;
    border-bottom-width: 5px;
    border-bottom-style: solid;
  }
  .hero.is-light a.navbar-item.is-active {
    background-color: rgba(10, 10, 10, 0.1);
  }
  .hero.is-light a.navbar-item:hover, .navbar-link:hover {
    background-color: #f7f8fa;
    border-color: #9164bc;
    border-bottom-width: 5px;
    border-bottom-style: solid;
    border-radius: 0px;
  }
  .hero.is-light a.navbar-item.is-active,
  .hero.is-light .navbar-link.is-active {
    background-color: #f7f8fa;
    border-bottom-color: #766C7F;
    border-bottom-width: 5px;
    border-bottom-style: solid;
    border-radius: 0px;
  }
  .hero.is-light a.home-logo.navbar-item:hover {
    border-color: transparent;
  }
  @media screen and (min-width: 769px), print {
    .hero.is-medium .hero-body {
        padding-bottom: 3rem;
        padding-top: 3rem;
    }
  }
  @media screen and (max-width: 1087px) {
    .hero.is-light .navbar-menu {
        background-color: #f7f8fa;
    }
  }
  @media screen and (max-width: 768px) {
    .hero.is-light.is-bold .navbar-menu {
        background-image: none;
    }
  }
  @media screen and (max-width: 480px) {
    .image.is-responsive {
      height: 96px;
      width: 96px;
    }
  }
</style>

<script>
  import { mapGetters } from 'vuex'

  export default {
    data () {
      return {
        section: String,
        isActive: false
      }
    },
    computed: {
      hideNav () {
        if (this.$route.name != null && (this.$route.name.includes('blog-post') || this.$route.name.includes('blog'))) {
          return false
        }
        return true
      },
      ...mapGetters([
        'post'
      ]),
      nextPost () {
        if (this.post != null && this.post.meta.next_post != null) {
          return this.post.meta.next_post
        } else {
          return null
        }
      },
      previousPost () {
        if (this.post != null && this.post.meta.previous_post != null) {
          return this.post.meta.previous_post
        } else {
          return null
        }
      },
      checkPosts () {
        if (this.nextPost === null && this.previousPost === null) {
          return null
        } else {
          return true
        }
      }
    },
    methods: {
      hamburgerToggle: function () {
        if (this.getWidth() <= 1087) {
          this.isActive = !this.isActive
        }
      },
      closeHamburger: function () {
        if (this.getWidth() <= 1087) {
          this.isActive = false
        }
      },
      getWidth: function () {
        return Math.max(
          document.body.scrollWidth,
          document.documentElement.scrollWidth,
          document.body.offsetWidth,
          document.documentElement.offsetWidth,
          document.documentElement.clientWidth
        )
      }
    }
  }
</script>
