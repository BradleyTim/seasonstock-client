<template>
  <div class="jersey-detail-page">
    <div v-if="jersey" class="details-wrapper">
      <div class="image-container">
        <img :src="jersey.image_url" alt="Jersey Image">
      </div>
      <div class="details-container">
        <h2 class="jersey-name">{{ jersey.name }}</h2>
        <p class="jersey-kit">{{ jersey.kit }} Kit</p>
        <p class="jersey-kit">Ksh. {{ jersey.price }}</p>
      </div>
    </div>
    <div v-if="loading" class="loading">
      loading...
    </div>
    <div v-if="error" class="error">
      error
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      jersey: null,
      error: null,
      loading: false
    }
  },
  created () {
    this.getJersey()
  },
  methods: {
    async getJersey () {
      const options = {
        headers: {
          Accept: 'application/json'
        }
      }

      const API_URL = `https://jerseystore-api.now.sh/api/v1/jerseys/${this.$route.params.id}`

      this.loading = true

      try {
        const response = await axios.get(API_URL, options)
        if (response.status === 200) {
          this.loading = false
          this.jersey = response.data.jersey
          console.log(response.data.jersey)
        }
      } catch (error) {
        this.error = true
      }
    }
  },
  head () {
    return {
      title: 'Jersey | Premier League',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Get Premier League Jerseys at an affordable price here at Seasons'
        }
      ]
    }
  }
}
</script>

<style scoped>
.jersey-detail-page {
  margin: 2rem auto;
  min-height: 70vh;
}

.details-wrapper {
  display: flex;
  justify-content: space-around;
}

.image-container {
  flex: 1;
}

.image-container img {
  width: 90%;
  margin: 0 auto;
}

.details-container {
  flex: 2;
  padding: 2rem 0;
}

.jersey-name {
  font-size: 2rem;
}

.jersey-kit, .jersey-price {
  font-size: 1.5rem;
  font-weight: 300;
}

@media screen and (max-width: 600px) {
  .details-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    text-align: center;
  }
}
</style>
