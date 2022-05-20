<template>
  <div class="container">
    <div class="wrapper-headline-collection">
      <div class="headline-collection">
        <h1 class="font-weight-normal text-dark text-center">
          One Place for Your Development Tools
        </h1>
        <p class="font-weight-light text-secondary text-center w-75 mx-auto">
          You can find any ideas, tools, illustration, design, or refrences here
          just by click and open it
        </p>
      </div>
    </div>
    <div class="list-collection">
      <div
        class="collection-item"
        v-for="(item, index) in collections"
        :key="index"
      >
        <NuxtLink
          :to="`collection/${item.name}/list-collection/${item._id}`"
          class="text-dark"
          style="text-decoration: none"
        >
          <h1 class="font-weight-normal text-center">{{ item.name }}</h1>
          <div class="img-collection-wrapper text-center">
            <img :src="item.imageUrl" alt="image-collection" />
          </div>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
import getColletion from '../../gql/collection/getCollection.gql'

export default {
  name: 'CollectionComponent',
  layout: 'default',
  apollo: {
    collections: {
      query: getColletion,
    },
  },
}
</script>