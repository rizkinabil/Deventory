<template>
  <section>
    <ApolloQuery
      :query="require('../../../gql/blog/getItemBlogByPk.gql')"
      :variables="{ id: _idBlog }"
    >
      <template v-slot="{ result: { loading, error, data } }">
        <div v-if="loading">
          <div
            class="spinner-border"
            style="width: 3rem; height: 3rem"
            role="status"
          >
            <span class="sr-only">Loading...</span>
          </div>
          <div
            class="spinner-grow"
            style="width: 3rem; height: 3rem"
            role="status"
          >
            <span class="sr-only">Loading...</span>
          </div>
        </div>

        <h3 v-if="error">An error occured</h3>

        <div v-else-if="data">
          <div
            class="wrapper-blog-img"
            id="wrp-blog-detail"
            :style="`background-image: url('${data.item_blog[0].poster_path}')`"
          >
            <div class="wrpr-back-button-blog container-fluid">
              <div class="component-detail">
                <div class="container">
                  <p
                    class="font-weight-light text-light"
                    style="max-width: 200px"
                  >
                    <span>
                      <img
                        src="../../../static/assets/images/arrow-left-white.svg"
                        alt="back"
                      />
                    </span>
                    Explore all blogs
                  </p>
                </div>
              </div>
            </div>
            <div class="title-blog-detail container-fluid">
              <div class="component-detail">
                <h1 class="font-weight-normal text-light container">
                  {{ data.item_blog[0].title }}
                </h1>
              </div>
            </div>
          </div>
          <div class="text-all-blog container">
            <div class="info-author-date mb-5 row">
              <div class="img-profile" id="img-profile">
                <div class="name-logo text-center text-light">
                  <h1>{{ data.item_blog[0].author.slice(0, 1) }}</h1>
                </div>
              </div>
              <div class="author col-md-9">
                <h3 class="font-weight-normal text-dark">
                  {{ data.item_blog[0].author }}
                </h3>
                <p class="font-weight-light text-graymuda">
                  {{
                    new Date(data.item_blog[0].upload_at).toLocaleString(
                      'default',
                      {
                        month: 'short',
                        day: 'numeric',
                        year: 'numeric',
                      }
                    )
                  }}
                </p>
              </div>
            </div>
            <div class="row">
              <div class="paragraph col-md-8">
                <p>{{ data.item_blog[0].paragraph }}</p>
              </div>
              <div class="discover-blog col-md-4">
                <h3 class="font-weight-bold text-dark">Discover Blog</h3>
                <hr />
                <div
                  class="list-blog"
                  v-for="(item, index) in item_blog"
                  :key="index"
                >
                  <p class="font-weight-light text-dark">
                    {{ item.blog.categories }}
                  </p>
                  <p
                    class="title-list-blog font-weight-bold text-dark"
                    @click="redirectTo(item)"
                  >
                    "{{ item.title }}"
                  </p>
                  <p class="font-weight-light text-graymuda">
                    {{
                      new Date(item.upload_at).toLocaleString('default', {
                        month: 'short',
                        day: 'numeric',
                      })
                    }}
                    ·
                    {{ item.author }}
                  </p>
                  <hr />
                </div>
              </div>
            </div>
          </div>
        </div>
      </template>
    </ApolloQuery>
  </section>
</template>

<script>
import getAllItemBlog from '../../../gql/blog/getAllItemBlog.gql'

export default {
  name: 'DetailBlogComponent',
  apollo: {
    item_blog: {
      query: getAllItemBlog,
    },
  },
  computed: {
    _idBlog() {
      return this.$route.params.id
    },
    randomColor() {
      return Math.floor(Math.random() * 16777215).toString(16)
    },
  },
  methods: {
    back() {
      this.$router.go(-1)
    },
    redirectTo(item) {
      this.$router.push(`/blog/${item.title}/${item._id}`)
    },
  },
  mounted() {
    // setup random color
    // var randomColor = Math.floor(Math.random() * 16777215).toString(16)
    // var configAutoBg = document.querySelector('.img-profile')
    // configAutoBg.style.backgroundColor = '#' + randomColor
  },
}
</script>

<style>
</style>