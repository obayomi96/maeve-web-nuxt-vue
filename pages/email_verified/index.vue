<template>
  <div id="login_bg">
    <nav id="menu" class="fake_menu"></nav>
    <div id="login">
      <aside>
        <figure>
          <nuxt-link to="/">
            <img
              src='~~/img/maeveLogo.png'
              width="155"
              height="36"
              data-retina="true"
              alt
              class="logo_sticky"
            />
          </nuxt-link>
        </figure>
      </aside>
    </div>
  </div>
</template>

<script>

export default {
  middleware: 'auth',

  data() {
    return {
      error: null
    }
  },

  methods: {
    created() {
      try {
          this.$axios.post('account/verify', {
            email: this.$router.params.email,
            code: this.$router.params.code,
          })
        this.error = 'Password reset successfully!';
        setTimeout(() => {
          this.$router.push('/profile')
        }, 2000)
      } catch (err) {
        const { errors } = err.response.data;
        this.error = errors[0].message
      }
    }  
  }
}
</script>
