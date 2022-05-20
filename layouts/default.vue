<template>
  <!-- navbar -->
  <section>
    <nav
      id="nav-element"
      class="
        navbar navbar-expand-lg
        wrapper-navbar
        is-transparent
        navbar-light
        fixed-top
      "
    >
      <div class="container">
        <brand-text-icon isDark />

        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarNavAltMarkup"
          aria-controls="navbarNavAltMarkup"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div
          class="collapse navbar-collapse d-flex justify-content-end"
          id="navbarNavAltMarkup"
        >
          <div class="navbar-nav">
            <NuxtLink class="nav-link" to="/">Home</NuxtLink>
            <NuxtLink class="nav-link" to="/collection">collection </NuxtLink>
            <NuxtLink class="nav-link" to="/blog">Blog</NuxtLink>
            <button class="btn btn-dark">
              <a
                class="font-weight-normal text-light"
                href="https://twitter.com/intent/tweet?url=https%3A%2F%2Fdeventory.netlify.app"
                rel="noopener"
                target="blank"
              >
                <i class="fab fa-2x fa-twitter"></i>Share
              </a>
            </button>
          </div>
        </div>
      </div>
    </nav>
    <!-- end of navbar -->

    <!-- main -->
    <Nuxt />

    <!-- end of main -->

    <div class="footer-wrapper">
      <div class="footer container">
        <div class="row">
          <div class="col-md-3">
            <brand-text-icon />
            <p class="font-weight-light text-graymuda mt-3">
              No need to bookmark your web tools references, just open this and
              all the thing is here :)
            </p>
          </div>
          <div class="col-md-9 d-flex">
            <div class="col-md-4">
              <h1 class="font-weight-normal">Collection</h1>

              <div
                class="footer-sublink font-weight-light"
                v-for="(item, index) in collections.slice(0, 4)"
                :key="index"
              >
                <ul>
                  <li>
                    <NuxtLink
                      :to="`/collection/${item.name}/list-collection/${item._id}`"
                      class="text-graymuda"
                      >{{ item.name }}</NuxtLink
                    >
                  </li>
                </ul>
              </div>
            </div>
            <div class="col-md-4">
              <h1 class="font-weight-normal">Blog</h1>
              <div class="footer-sublink font-weight-light">
                <ul>
                  <li>
                    <NuxtLink to="/blog" class="text-graymuda"
                      >Discover Blog</NuxtLink
                    >
                  </li>
                </ul>
              </div>
            </div>
            <div class="col-md-4">
              <h1 class="font-weight-normal">Contact</h1>
              <div class="footer-sublink font-weight-light">
                <ul>
                  <li class="mb-3">
                    <a href="#" class="text-graymuda">0821-1277-6194</a>
                  </li>
                  <li class="mb-3">
                    <a href="#" class="text-graymuda">rizki.nbl123@gmail.com</a>
                  </li>

                  <li class="mb-3">
                    <a href="#" class="text-graymuda"
                      >Deventory, Kemang, Jakarta.</a
                    >
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
        <div class="row bottom-footer">
          <p class="font-weight-light text-graymuda">
            Copyright 2022 • All rights reserved • Deventory
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
// brandIcon component
import brandTextIcon from '../components/BrandIcon/index.vue'

// collection
import getCollection from '../gql/collection/getCollection.gql'

// blog
import getBlog from '../gql/blog/getBlog.gql'

export default {
  name: 'Navbar',
  components: {
    brandTextIcon,
  },
  mounted() {
    this.$nextTick(function () {
      window.addEventListener('scroll', function () {
        var navbar = document.getElementById('nav-element')
        var nav_classes = navbar.classList

        if (document.documentElement.scrollTop >= 150) {
          if (nav_classes.contains('shrink') === false) {
            nav_classes.toggle('shrink')
          }
        } else {
          if (nav_classes.contains('shrink') === true) {
            nav_classes.toggle('shrink')
          }
        }
      })
    })
  },
  apollo: {
    collections: {
      query: getCollection,
    },
    blogs: {
      query: getBlog,
    },
  },
}
</script>

<style lang="scss">
</style>