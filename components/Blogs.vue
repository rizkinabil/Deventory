<template>
  <div class="container blog-wrapper">
    <div class="blog-head d-flex">
      <img src="../static/assets/images/blogs/blog-icon.svg" alt="icon" />
      <h2 class="font-weight-normal">Blogs</h2>
    </div>
    <div class="wrapper-blog-content">
      <div v-for="(item, index) in item_blog" :key="index">
        <NuxtLink
          :to="`/blog/${item.blog.categories}/${item._id}`"
          class="text-dark d-flex blog-content"
          style="text-decoration: none"
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
        </NuxtLink>
      </div>
      <div class="see-more-wrapper d-flex">
        <div class="arrow">
          <img src="../static/assets/images/blogs/blog-arrow.svg" alt="arrow" />
        </div>

        <div class="see-more">
          <NuxtLink to="/blog" class="text-dark" style="text-decoration: none">
            <h1 class="font-weight-bold">See More...</h1>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import getAllItemBlogHome from '../gql/blog/getAllItemBlogHome.gql'

export default {
  name: 'BlogsComponent',
  apollo: {
    item_blog: {
      query: getAllItemBlogHome,
    },
  },
}
</script>

<style>
</style>