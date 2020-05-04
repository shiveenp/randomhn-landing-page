<template>
  <div class="container">
    <section class="hero is-medium">
      <div class="hero-body">
        <div class="container">
          <figure class="image container is-128x128">
            <img src="~/assets/random_hn_icon.png" />
          </figure>
          <h1 class="title has-text-centered">
            Random HN
          </h1>
          <p class="subtitle has-text-centered">
            Click the button below and it will take you to a random hacker news
            story. HN is a great place to discover, read and take part in
            various topics and discussions. Unlike other platforms (like
            twitter, reddit etc.) HN provides a more nuanced and focused
            discussion platform.
          </p>
          <div class="has-text-centered">
            <b-button
              :loading="isLoading"
              @click="takeToNewHnLink"
              class="hn-theme"
              >Jump In 🚀</b-button
            >
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HomePage',
  data() {
    return {
      isLoading: false
    }
  },
  methods: {
    takeToNewHnLink() {
      this.isLoading = true
      axios
        .get(
          'https://qxjoqsucf5.execute-api.ap-southeast-2.amazonaws.com/default/randomhn'
        )
        .then(response => {
          this.isLoading = false
          const itemId = response.data
          window.location = `https://news.ycombinator.com/item?id=${itemId}`
        })
        .catch(error => {
          console.log(error)
          this.isLoading = false
        })
    }
  }
}
</script>

<style scoped>
.hn-theme {
  background-color: #FF6D00;
}
</style>
