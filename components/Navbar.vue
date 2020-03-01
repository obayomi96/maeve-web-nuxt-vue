<template>
  <nav class="navbar is-light" w="100">
    <div class="container">
      <div class="navbar-brand">
        <nuxt-link class="navbar-item" to="/">
          <img src='../img/maeveLogo.png' alt="Maeve Logo" />
        </nuxt-link>
        <button class="button navbar-burger">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
      <div class="navbar-menu">
        <div class="navbar-end">
          <div v-if="$auth.loggedIn" class="navbar-item has-dropdown is-hoverable" >
            <a class="navbar-link">
            </a>
            <div class="navbar-dropdown">
              <nuxt-link class="navbar-item" to="/profile">My Profile</nuxt-link>
              <hr class="navbar-divider">
              <a class="navbar-item" @click="logout">Logout</a>
                 <hr class="navbar-divider">
              <!-- <nuxt-link class="navbar-item" to="/experience">Experiences</nuxt-link> -->
               <hr class="navbar-divider">
              <nuxt-link class="navbar-item" to="/experience">Experience Lists</nuxt-link>
               <hr class="navbar-divider">
              <nuxt-link class="navbar-item" to="/update-password">Password reset</nuxt-link>
            </div>
          </div>
          <template v-else >
            <nuxt-link class="navbar-item" to="/register">Register</nuxt-link>
            <nuxt-link class="navbar-item" to="/login">Log In</nuxt-link>
          </template>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  methods: {
    logout() {
      this.$auth.logout()
    },
  }
}
</script>

<style scoped>
  .navbar {
    width: 100%;
    margin-top: 0;
  }
</style>