<template>
  <div class="jersey-detail-page" :class="{'loading-or-error': !jersey}">
    <div v-if="jersey" class="details-wrapper">
      <div class="image-container">
        <img :src="jersey.image_url" alt="Jersey Image">
      </div>
      <div class="details-container">
        <h2 class="jersey-name">
          {{ jersey.name }}
        </h2>
        <p class="jersey-kit">
          {{ jersey.kit }} Kit
        </p>
        <p class="jersey-kit">
          Ksh. {{ jersey.price }}
        </p>
      </div>
    </div>
    <app-loading v-if="loading" />
    <app-error v-if="error" />
  </div>
</template>

<script>
import axios from 'axios'
import AppError from '~/components/AppError.vue'
import AppLoading from '~/components/AppLoading.vue'

export default {
  components: {
    AppError,
    AppLoading
  },
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
        }
      } catch (error) {
        this.loading = false
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
  margin: 4rem auto;
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
  font-weight: 400;
}

@media screen and (max-width: 600px) {
  .details-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    text-align: center;
  }

  .image-container img {
    width: 80%;
    margin: 0 auto;
  }
}
</style>
