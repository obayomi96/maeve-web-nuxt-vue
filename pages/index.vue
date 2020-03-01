<template>
<div>
  <Navbar />
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        experience_web
      </h1>
      <nuxt-link to="/login">
        Sign In |
      </nuxt-link>
      <nuxt-link to="/register">
        Sign Up |
      </nuxt-link>
      <!-- <nuxt-link to="/experience">
        experience |
      </nuxt-link>
      <nuxt-link to="/experience-listing">
        experience listing |
      </nuxt-link> -->
      <nuxt-link to="/search-experience">
        search result page
      </nuxt-link>
    </div>
  </div>
</div>
</template>

<script>
import Logo from '~/components/Logo.vue';
import Navbar from '~/components/Navbar.vue';

export default {

  components: {
    Logo,
    Navbar
  },
}
</script>
