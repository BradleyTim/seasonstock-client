<template>
  <div class="index-page">
    <div v-if="jerseys" class="jerseys-list">
      <div v-for="jersey in jerseys" :key="jersey._id" class="jersey-card">
        <img class="jersey-image" :src="jersey.image_url" alt="Jersey">
        <div class="best-seller">
          BEST SELLER
        </div>
        <h3 class="jersey-title">
          <nuxt-link :to="`/jerseys/${jersey._id}`">
            {{ jersey.name }} {{ jersey.kit }} kit
          </nuxt-link>
        </h3>
        <p class="jersey-price">
          Ksh. {{ jersey.price }}
        </p>
      </div>
    </div>
    <div v-if="error" class="error">
      Ooops! There was an Error...try again later
    </div>
    <div v-if="loading" class="loading">
      <img class="loading" src="../assets/Spinner-1s-200px.svg" alt="Spinner">
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  components: {},
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
  margin: 2rem auto;
  min-height: 100vh;
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
    width: 80%;
  }

  .best-seller {
    width: 30%;
    margin: .5rem auto;
  }
}
</style>
