<template>
  <div class="container blog-wrapper">
    <div class="blog-head d-flex">
      <img src="../static/assets/images/blogs/blog-icon.svg" alt="icon" />
      <h2 class="font-weight-normal">Blogs</h2>
    </div>
    <div class="wrapper-blog-content">
      <div
        class="blog-content d-flex"
        v-for="(item, index) in item_blog.slice(0, 5)"
        :key="index"
      >
        <div class="col-2 blog-index">
          <h1 class="font-weight-bold">0{{ index + 1 }}</h1>
        </div>
        <div class="col-10 blog-title">
          <div class="row pt-2">
            <p class="font-weight-light text-dark">
              {{ item.blog.categories }}
            </p>
          </div>
          <div class="row">
            <h1 class="font-weight-bold">"{{ item.title }}"</h1>
          </div>
          <div class="row date">
            <p class="font-weight-light upload-at text-graymuda">
              {{
                new Date(item.upload_at).toLocaleString('default', {
                  month: 'short',
                  day: 'numeric',
                })
              }}
              ·
              {{ item.author }}
            </p>
          </div>
        </div>
      </div>
      <div class="see-more-wrapper d-flex">
        <div class="arrow">
          <img src="../static/assets/images/blogs/blog-arrow.svg" alt="arrow" />
        </div>

        <div class="see-more">
          <h1 class="font-weight-bold">See More...</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import getAllItemBlog from '../gql/blog/getAllItemBlog.gql'

export default {
  name: 'BlogsComponent',
  apollo: {
    item_blog: {
      query: getAllItemBlog,
    },
  },
}
</script>

<style>
</style>