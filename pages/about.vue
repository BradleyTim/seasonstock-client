<template>
  <div class="about">
    <h3 class="about-title">
      About Us
    </h3>
  </div>
</template>

<script>

export default {
  components: {},
  head () {
    return {
      title: 'About Us',
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

<style>
.about {
  width: 90%;
  margin: 5rem auto;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.about-title {
  font-size: 2rem;
  font-weight: 300;
}
</style>
