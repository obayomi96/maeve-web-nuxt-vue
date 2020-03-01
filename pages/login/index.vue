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
          <Notification :message="error" v-if="error"/>
        <form method="post" @submit.prevent="loginUser">
          <div class="form-group">
            <label for="email">Email</label>
            <input v-model="email" type="email" class="form-control" name="email" id="email" required />
            <i class="icon_mail_alt"></i>
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input v-model="password" type="password" class="form-control" name="password" id="password" required />
            <i class="icon_lock_alt"></i>
          </div>
          <div class="clearfix add_bottom_30">
            <div class="checkboxes float-left">
              <label class="container_check">
                Remember me
                <input type="checkbox" />
                <span class="checkmark"></span>
              </label>
            </div>
            <div class="float-right mt-1">
              <strong>
              <nuxt-link to="/forgot_password">
                Forgot Password?
              </nuxt-link>
            </strong>
            </div>
          </div>
          <div @click.prevent="loginUser" class="btn_1 rounded full-width">Login to Maeve</div>
          <div class="text-center add_top_10">
            New to Maeve?
            <strong>
              <nuxt-link to="/register">
                Sign up!
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
      email: '',
      password: '',
      error: ''
    }
  },


  methods: {
    async loginUser() {
      try {
        await this.$auth.loginWith('local', {
          data: {
            email: this.email,
            password: this.password
          }
        })
        this.$router.push('/profile')
      } catch (err) {
        if (err) {
          const { errors } = err.response.data;
          this.error = errors[0].message;
        }
      }
      }
    }, 
  }
</script>
