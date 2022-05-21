<template>
  <section>
    <hero-section v-on:scrollTo="scrollElement" />
    <collection-section />
    <blog-section />
    <banner-section />
  </section>
</template>

<script>
import HeroSection from '../components/Hero.vue'
import CollectionSection from '../components/Collections.vue'
import BlogSection from '../components/Blogs.vue'
import BannerSection from '../components/Banner.vue'

export default {
  name: 'IndexPage',
  components: {
    HeroSection,
    CollectionSection,
    BlogSection,
    BannerSection,
  },
  methods: {
    scrollElement() {
      window.scrollTo({ top: 720, behavior: 'smooth' })
    },
  },
}
</script>

