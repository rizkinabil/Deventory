<template>
  <div>
    <section v-if="isBig">
      <a
        href="/"
        class="navbar-brand-logo font-weight-bold"
        style="font-size: 2.25rem"
      >
        {dev}<span class="font-weight-light text-dark">entory</span
        ><span class="text-red">.</span>
      </a>
    </section>
    <section v-else>
      <a
        href="/"
        class="navbar-brand-logo font-weight-bold"
        style="font-size: 1.5rem"
      >
        <section v-if="isDark">
          {dev}<span class="font-weight-light text-dark">entory</span
          ><span class="text-red">.</span>
        </section>
        <section v-else>
          {dev}<span class="font-weight-light text-light">entory</span
          ><span class="text-red">.</span>
        </section>
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
    isDark: {
      type: Boolean,
    },
  },
}
</script>

<style>
</style>