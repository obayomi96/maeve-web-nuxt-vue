<template>
<div>
  <Navbar />
  <section class="section">
    <div class="container">
      <h2 class="title">My Profile</h2>
      <div class="content">
        <p>
          <strong>Email:</strong>
          {{ $auth.user.email }}
        </p>
        <p>
          <strong>Firstname:</strong>
           {{ $auth.user.firstName }}
        </p>
        <p>
          <strong>Lastname:</strong>
           {{ $auth.user.lastName }}
        </p>
      </div>
    </div>
  </section>
</div>
</template>

<script>
import Navbar from '~/components/Navbar.vue';


export default {

  components: {
    Navbar
  },

  middleware: 'auth',
}
</script>
