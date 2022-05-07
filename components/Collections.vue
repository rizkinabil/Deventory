<template>
  <div class="container collection-wrapper">
    <div class="collection-title d-flex">
      <img
        src="../static/assets/images/collections/collection-icon.jpg"
        alt=""
      />
      <h2 class="font-weight-normal">Collections</h2>
    </div>
    <div class="card-wrapper d-flex">
      <div class="custom-card" id="card-1">
        <h1 class="font-weight-normal text-light">Learning Resources</h1>
        <div class="svg-1">
          <img
            src="../static/assets/images/collections/collection-illustration-1.svg"
            alt="illustration"
          />
        </div>
      </div>
      <div class="custom-card" id="card-2">
        <h1 class="font-weight-normal text-light">Design Ideas</h1>
        <div class="svg-2">
          <img
            src="../static/assets/images/collections/collection-illustration-2.svg"
            alt="illustration"
          />
        </div>
      </div>
      <div class="custom-card" id="card-3">
        <h1 class="font-weight-normal">Illustrations</h1>
        <div class="svg-3">
          <img
            src="../static/assets/images/collections/collection-illustration-3.svg"
            alt="illustration"
          />
        </div>
      </div>
      <div class="custom-card">
        <div>
          <img
            class="arrow-right"
            src="../static/assets/images/collections/collection-arrow.jpg"
            alt=""
          />
        </div>
        <div class="bottom-title">
          <h1 class="font-weight-normal">Keep Explore</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CollectionComponent',
}
</script>

<style>
</style>