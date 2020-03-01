<template>
  <div id="register_bg">
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
        <form autocomplete="off" @submit.prevent="registerUser">
          <div class="form-group">
            <label>First Name</label>
            <input v-model="firstName" class="form-control" type="text" />
            <i class="ti-user"></i>
          </div>
          <div class="form-group">
            <label>Last Name</label>
            <input v-model="lastName" class="form-control" type="text" />
            <i class="ti-user"></i>
          </div>
          <div class="form-group">
            <label>Your Email</label>
            <input v-model="email" class="form-control" type="email" />
            <i class="icon_mail_alt"></i>
          </div>
          <div class="form-group">
            <label>Your Password</label>
            <input v-model="password" class="form-control" type="password" id="password1" />
            <i class="icon_lock_alt"></i>
          </div>
          <div class="form-group">
            <label>Confirm Password</label>
            <input v-model="password2" name="password2" class="form-control" type="password" id="password2" />
            <i class="icon_lock_alt"></i>
          </div>
          <div id="pass-info" class="clearfix"></div>
          <div @click.prevent="registerUser" class="btn_1 rounded full-width add_top_30">Register Now!</div>
          <div class="text-center add_top_10">
            Already have an acccount?
            <strong>
              <nuxt-link to="/login">
                Sign In
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
      firstName: '',
      lastName: '',
      email: '',
      password: '',
      password2: '',
      error: ''
    }
  },

  methods: {
    async registerUser() {
      if (this.password === this.password2) {
        try {
          await this.$axios.post('/account/signUp', {
            firstName: this.firstName,
            lastName: this.lastName,
            email: this.email,
            password: this.password
          })
  
          await this.$auth.loginWith('local', {
            data: {
              email: this.email,
              password: this.password
            },
          })
          this.error = 'Registration successfull, check your email to verify your account';
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