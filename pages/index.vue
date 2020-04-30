<template>
  <div class="container">
    <section class="hero is-medium">
      <div class="hero-body">
        <div class="container">
          <h1 class="title has-text-centered">
            Random HN
          </h1>
          <p class="subtitle has-text-centered">
            Click the button below and it will take you to a random HN story. HN is a great place to discover, read and take part in various topics and discussions. Unlike other platforms (like twitter, reddit etc.) HN provides a more nuanced and focussed discussion platform.
          </p>
        </div>
      </div>
    </section>
    <section>
      <div class="has-text-centered">
        <b-button @click="takeToNewHnLink" class="hn-theme">Take Me Somewhere</b-button>
      </div>
    </section>
    <section>
    </section>
  </div>
</template>

<script>
  export default {
    name: 'HomePage',
    methods: {
      takeToNewHnLink() {
        window.location = 'https://qxjoqsucf5.execute-api.ap-southeast-2.amazonaws.com/default/randomhn';
      }
    }
  }
</script>

<style scoped>
  .hn-theme {
    background-color: orange;
  }
</style>
