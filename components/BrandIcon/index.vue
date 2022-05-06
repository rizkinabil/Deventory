<template>
  <div>
    <section v-if="isBig">
      <a
        id="brand-icon"
        href="/"
        class="navbar-brand-logo font-weight-bold"
        style="font-size: 2.25rem"
      >
        {dev}<span class="font-weight-light">entory</span
        ><span id="titik">.</span>
      </a>
    </section>
    <section v-else>
      <a
        id="brand-icon"
        href="/"
        class="navbar-brand-logo font-weight-bold"
        style="font-size: 1.5rem"
      >
        {dev}<span class="font-weight-light">entory</span
        ><span id="titik">.</span>
      </a>
    </section>
  </div>
</template>

<script>
export default {
  name: 'BrandIcon',
  props: {
    isBig: {
      type: Boolean,
    },
  },
}
</script>

<style>
</style>