<template>
  <div class="container">
    <div class="wrapper-item-collection">
      <div class="back-button d-flex" @click="() => this.$router.go(-1)">
        <img src="../../../../static/assets/images/arrow-left.svg" alt="back" />
        <p class="font-weight-light">Explore all collections</p>
      </div>
      <ApolloQuery
        :query="require('../../../../gql/collection/getItemCollectionByFk')"
        :variables="{ collectionId: _idCollection }"
      >
        <template v-slot="{ result: { error, data }, isLoading }">
          <div class="wrapper-loading" v-if="isLoading">
            <div>
              <trinity-rings-spinner
                :animation-duration="1500"
                :size="66"
                color="#ff1d5e"
              />
            </div>
          </div>

          <h3 v-else-if="error">An error occured</h3>

          <div v-else-if="data" class="wrapper-content-item-col">
            <div class="header-content-item-col">
              <h1 class="font-weight-normal text-dark">
                {{ data.item_collection[0].collection.name }}
              </h1>
              <p class="font-weight-light text-secondary">
                {{ data.item_collection[0].collection.description }}
              </p>
            </div>
            <div
              class="card-item-col mt-5"
              v-for="(item, index) in data.item_collection"
              :key="index"
            >
              <div class="row">
                <div class="col-md-4">
                  <h1 class="font-weight-normal text-dark">
                    {{ item.web_name }}
                  </h1>
                  <p class="font-weight-light text-graymuda">
                    {{ trunc(item.description, 150) }}
                  </p>
                  <a
                    :href="`${item.web_url}`"
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    <button class="btn-custom-lg font-weight-normal">
                      Learn more
                      <span
                        ><img
                          src="../../../../static/assets/images/learn-more.svg"
                          alt=""
                      /></span>
                    </button>
                  </a>
                </div>
                <div class="col-md-8 wrapper-card-img">
                  <img :src="item.poster_path" alt="image" />
                </div>
              </div>
            </div>
          </div>
        </template>
      </ApolloQuery>
    </div>
  </div>
</template>

<script>
import util from '../../../../utils/util'
import { TrinityRingsSpinner } from 'epic-spinners'

export default {
  name: 'ItemCollectionComponent',
  layout: 'default',
  components: {
    TrinityRingsSpinner,
  },
  computed: {
    _idCollection() {
      return this.$route.params.id
    },
  },
  methods: {
    trunc(str, num) {
      return util.truncateString(str, num)
    },
  },
}
</script>

<style>
</style>