<template>
  <section>
    <hero-section />
    <collection-section ref="start" />
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
}
</script>

