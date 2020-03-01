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
        <form method="post" @submit.prevent="updatePassword">
          <div class="form-group">
            <label>New password</label>
            <input v-model="password" type="password" class="form-control" name="password" id="password" value />
            <i class="icon_lock_alt"></i>
          </div>
          <div class="form-group">
            <label>Confirm new password</label>
            <input v-model="password2" name="password2" class="form-control" type="password" id="password2" />
            <i class="icon_lock_alt"></i>
          </div>
          <div @click.prevent="updatePassword" class="btn_1 rounded full-width">Update password</div>
        </form>
        <div class="copy">© 2020 Maeve</div>
      </aside>
    </div>
  </div>
</template>

<script>

export default {
    middleware: 'auth',

  data() {
    return {
      password: '',
      password2: '',
      error: null
    }
  },

  methods: {
    async updatePassword() {
      if (this.password === this.password2) {
      try {
          await this.$axios.post('https://affinity-ng.herokuapp.com/account/update-password', {
            id: this.$router.params.id,
            password: this.password,
          })
        this.error = 'Password reset successfully!';
        setTimeout(() => {
          this.$router.push('/profile')
        }, 2000)
      } catch (err) {
        if(err) {
          const { errors } = err.response.data;
          this.error = errors[0].message;
        }
      }
      } else {
        this.error = 'Passwords do not match';
      }
    }
  }
}
</script>