<template>
  <div class="index-page">
    <app-jersey-list v-if="jerseys" :jerseys="jerseys" />
    <app-error v-if="error" />
    <app-loading v-if="loading" />
  </div>
</template>

<script>
import axios from 'axios'
import AppJerseyList from '~/components/AppJerseyList.vue'
import AppError from '~/components/AppError.vue'
import AppLoading from '~/components/AppLoading.vue'

export default {
  components: {
    AppError,
    AppLoading,
    AppJerseyList
  },
  data () {
    return {
      jerseys: null,
      error: null,
      loading: false
    }
  },
  created () {
    this.getJerseys()
  },
  methods: {
    async getJerseys () {
      const options = {
        headers: {
          Accept: 'application/json'
        }
      }

      const API_URL = 'https://jerseystore-api.now.sh/api/v1/jerseys'

      this.loading = true

      try {
        const response = await axios.get(API_URL, options)
        if (response.status === 200) {
          this.loading = false
          this.jerseys = response.data.jerseys
        }
      } catch (error) {
        this.loading = false
        this.error = true
      }
    }
  },
  head () {
    return {
      title: 'Seasons - We Stock All Jerseys',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'We are all about Premier League Jerseys and Kits'
        }
      ]
    }
  }
}
</script>

<style scoped>
.index-page {
  margin: 4rem auto;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.jerseys-list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem;
}

.jersey-card {
  /* border: 1px solid #eee; */
  text-align: center;
}

.jersey-image {
  width: 70%;
  margin: 0 auto;
}

.jersey-title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 1.25rem;
  color: #35495e;
  letter-spacing: 1px;
}

.jersey-price {
  font-weight: 300;
  font-size: 1.25rem;
  color: #526488;
  word-spacing: 5px;
}

.best-seller {
  width: 25%;
  margin: 0 auto;
  background: yellow;
  padding: .25rem;
}

@media screen and (max-width: 600px) {
  .jerseys-list {
    display: grid;
    grid-template-columns: 1fr;
    grid-row-gap: 1.5rem;
  }

  .jersey-card {
    padding-bottom: 1.5rem;
    border-bottom: 1px solid #eee;
  }

  .jersey-image {
    width: 50%;
  }

  .best-seller {
    width: 30%;
    margin: .5rem auto;
  }
}
</style>
