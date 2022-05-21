<template>
  <div class="wrapper-hero text-center">
    <brand-text-icon isBig />
    <div class="headline">
      <h1 class="font-weight-normal">
        All in One Place for Front-end Development Tools
      </h1>
    </div>
    <div class="description">
      <p class="font-weight-light text-secondary">
        No need to bookmark your web tools references, just open this and all
        the thing is here :)
      </p>
    </div>
    <div class="cta-button">
      <button
        class="btn-custom-lg font-weight-normal"
        @click="() => this.$emit('scrollTo')"
      >
        Let's Start
      </button>
      <NuxtLink to="/blog" class="text-dark ml-3">See Blog</NuxtLink>
    </div>
  </div>
</template>

<script>
import brandTextIcon from '../components/BrandIcon/index.vue'
export default {
  name: 'HeroSection',
  components: {
    brandTextIcon,
  },
  emits: ['scrollTo'],
}
</script>

<style lang="scss">
</style>