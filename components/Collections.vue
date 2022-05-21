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
      <NuxtLink
        :to="`/collection/${collections[0].name}/list-collection/${collections[0]._id}`"
        style="text-decoration: none"
        class="custom-card-collection"
        id="card-1"
      >
        <h1 class="font-weight-normal text-light">
          {{ collections[0].name }}
        </h1>
        <div class="svg-1">
          <img
            src="../static/assets/images/collections/collection-illustration-1.svg"
            alt="illustration"
          />
        </div>
      </NuxtLink>

      <NuxtLink
        :to="`/collection/${collections[1].name}/list-collection/${collections[1]._id}`"
        style="text-decoration: none"
        class="custom-card-collection"
        id="card-2"
      >
        <h1 class="font-weight-normal text-light">
          {{ collections[1].name }}
        </h1>
        <div class="svg-2">
          <img
            src="../static/assets/images/collections/collection-illustration-2.svg"
            alt="illustration"
          />
        </div>
      </NuxtLink>

      <NuxtLink
        :to="`/collection/${collections[2].name}/list-collection/${collections[2]._id}`"
        style="text-decoration: none"
        class="custom-card-collection text-dark"
        id="card-3"
      >
        <h1 class="font-weight-normal">{{ collections[2].name }}</h1>
        <div class="svg-3">
          <img
            src="../static/assets/images/collections/collection-illustration-3.svg"
            alt="illustration"
          />
        </div>
      </NuxtLink>
      <NuxtLink to="/collection" class="text-dark">
        <div class="custom-card-collection">
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
      </NuxtLink>
    </div>
  </div>
</template>

<script>
import getCollection from '../gql/collection/getCollection.gql'

export default {
  name: 'CollectionComponent',
  apollo: {
    collections: {
      query: getCollection,
    },
  },
}
</script>

<style>
</style>