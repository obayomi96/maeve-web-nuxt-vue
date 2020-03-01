<template>
  <div id="login_bg">
    <nav id="menu" class="fake_menu"></nav>
    <div id="login">
      <aside>
        <figure>
          <div class="logo-box">
            <nuxt-link to="/">
              <img class="logo-icon-web" alt="" src="../../img/icons/logo.png" />
            </nuxt-link>
          </div>
        </figure>
        <Notification v-if="error" :message="error" />
        <form @submit.prevent="resetPassword">
          <div class="form-group">
            <label>Please confirm login email below</label>
            <input v-model="email" type="email" class="form-control" name="email" id="email" />
            <i class="icon_mail_alt"></i>
          </div>
          <div class="clearfix add_bottom_30">
         You will receive an email containing a link allowing you to reset your password to a new preferred one.
          </div>
          <div @click="resetPassword" class="btn_1 rounded full-width">Reset Password</div>
          <div class="text-center add_top_10">
            Already have an account?
            <strong>
              <nuxt-link to="/login">
                Sign In!
              </nuxt-link>
            </strong>
          </div>
        </form>
        <div class="copy">© 2020 Maeve</div>
      </aside>
    </div>
  </div>
</template>

<script>
import Notification from '~/components/Notification';

export default {

  components: {
    Notification,
  },

  data() {
    return {
      email: "",
      error: ''
    }
  },

  methods: {
    async resetPassword() {
      try {
          await this.$axios.post('/account/password-reset', {
            email: this.email,
          })
        this.error = 'Check your email address for reset password link';
      } catch (err) {
        if (err) {
          const { errors } = err.response.data;
          this.error = errors[0].message;
        }
      }
    }
  }
}
</script>