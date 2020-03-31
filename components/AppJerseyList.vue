<template>
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
</template>

<script>
export default {
  name: 'AppJerseyList',
  props: {
    jerseys: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
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
  /* font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif; */
  display: block;
  font-weight: 300;
  font-size: 1.15rem;
  /* color: #35495e; */
  color: #2c3e50;
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
    font-size: .9rem;
    width: 30%;
    margin: .5rem auto;
  }
}
</style>
