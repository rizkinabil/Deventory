<template>
  <!-- navbar -->
  <section>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container">
        <brand-text-icon :isBig="false" />

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
            <a class="nav-link" href="#">Home</a>
            <a class="nav-link" href="#">Collection</a>
            <a class="nav-link" href="#">Blog</a>
            <button class="btn btn-dark font-weight-normal">Share</button>
          </div>
        </div>
      </div>
    </nav>
    <!-- end of navbar -->

    <!-- main -->
    <Nuxt />

    <!-- end of main -->

    <div class="footer-wrapper">
      <div class="footer container d-flex">
        <div class="col-md-5">
          <h1>{dev}entory</h1>
        </div>
        <div class="col-md-7">
          <div class="row">
            <div class="col-sm-4">
              <h1>collection</h1>
            </div>
            <div class="col-sm-4">
              <h1>Blog</h1>
            </div>
            <div class="col-sm-4">
              <h1>Contact</h1>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
// brandIcon component
import brandTextIcon from '../components/BrandIcon/index.vue'

export default {
  name: 'Navbar',
  components: {
    brandTextIcon,
  },
}
</script>

<style lang="scss">
</style>