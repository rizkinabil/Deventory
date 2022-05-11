<template>
  <div class="container wrapper-list-blog">
    <div class="head-blog text-center">
      <h1 class="font-weight-normal text-dark">Discover Blog</h1>
      <p class="font-weight-light text-graymuda">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ducimus,
        doloribus!
      </p>
    </div>
    <div class="card-display">
      <div
        class="custom-card-blog"
        v-for="(item, index) in item_blog"
        :key="index"
      >
        <div class="img-head">
          <img :src="item.poster_path" alt="poster" />
        </div>
        <div class="detail-info-blog">
          <p class="text-graymuda">{{ item.blog.categories }}</p>
          <h1 class="font-weight-normal">
            {{ item.title }}
          </h1>
          <p class="preview-text text-graymuda">
            {{ trunc(item.preview_text, 80) }}
          </p>
          <h3 class="font-weight-normal">
            READ MORE
            <span
              ><img src="../../static/assets/images/arrow-right.svg" alt=""
            /></span>
          </h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import getAllItemBlog from '../../gql/blog/getAllItemBlog.gql'

import util from '../../utils/util'

export default {
  name: 'ListBlogComponent',
  methods: {
    trunc(str, num) {
      return util.truncateString(str, num)
    },
  },
  apollo: {
    item_blog: {
      query: getAllItemBlog,
    },
  },
}
</script>

<style>
</style>