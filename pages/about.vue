<template>
  <div class=".about">
    <h3 class="about--title">
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
  margin: 0 auto;
}

.about--title {
  font-size: 50px;
  font-weight: 300;
}
</style>
