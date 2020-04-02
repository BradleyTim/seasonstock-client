<template>
  <section class="add-jersey-page">
    <div class="title">ADD JERSEY</div>
    <form enctype="multipart/form-data" v-if="!loading" @submit.prevent="addJersey">
      <input v-model="jersey.name" type="text" name="name" placeholder="name" required>
      <input v-model="jersey.price" type="text" name="price" placeholder="price" required>
      <input v-model="jersey.kit" type="text" name="kit" placeholder="kit" required>
      <input type="file" name="image" placeholder="image" @change="onFileChange" required>
      <button type="submit" class="btn">
        Add New Jersey
      </button>
    </form>
    <app-loading v-if="loading" />
  </section>
</template>

<script>
import axios from 'axios'
import AppLoading from '~/components/AppLoading.vue'

export default {
  components: {
    AppLoading
  },
  data () {
    return {
      jersey: {
        name: null,
        image: null,
        price: null,
        kit: null
      },
      loading: false,
      error: null
    }
  },
  methods: {
    onFileChange (e) {
      const files = e.target.files || e.dataTransfer.files
      if (files.length) {
        this.jersey.image = files[0]
      }
    },
    async addJersey () {
      console.log('running')
      const options = {
        headers: {
          Accept: 'application/json',
          'Content-type': 'multipart/form-data'
        }
      }

      const { name, image, price, kit } = this.jersey
      const fd = new FormData()
      fd.append('name', name)
      fd.append('image', image)
      fd.append('price', price)
      fd.append('kit', kit)
      const API_URL = 'https://jerseystore-api.now.sh/api/v1/jerseys'

      this.loading = true

      if (this.jersey.name !== '') {
        try {
          const response = await axios.post(API_URL, fd, options)
          console.log(response)
          if (response.status === 201) {
            this.loading = false
            this.jersey = {
              name: null,
              image: null,
              price: null,
              kit: null
            }
          }
        } catch (error) {
          console.log(error)
          this.loading = false
          this.error = true
        }
      }
    }
  }
}
</script>

<style scoped>
.add-jersey-page {
  margin: 4rem 0;
}

input {
  margin: 1rem 0;
}

.title {
  font-size: 1.35rem;
  font-weight: 700;
  letter-spacing: 1px;
  color: #777;
}
</style>
