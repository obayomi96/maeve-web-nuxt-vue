<template>
  <div>
    <div class="sec-nav" :class="[sticky ? 'sticky' : '']">
      <div class="logo-box">
        <nuxt-link to="/">
          <img class="logo-icon-web" alt="" src="../img/icons/logo.png" />
        </nuxt-link>
      </div>
      <div>
        <ul class="nav-items">
          <li>HOME</li>
          <li>DINING</li>
          <li>ADVENTURES</li>
          <li>DAY OUT</li>
        </ul>
      </div>
      <div class="search-bar">
        <img class="magnifying-glass" alt="" src="../img/icons/magnifying-glass-icon.png" />
        <form @submit.prevent="onSubmit">
          <input placeholder="Search" v-model="text"/>
        </form>
      </div>
    </div>
    <div class="sec-nav-mobile" :class="[sticky ? 'sticky' : '']">
      <div class="bread-crumb" role="button" @click="$store.dispatch('nav/toggleSidebar')">
        <div class="crumb-bar"></div>
        <div class="crumb-bar"></div>
        <div class="crumb-bar"></div>
      </div>
      <div>
        <nuxt-link to="/">
          <img class="logo-icon-mobile" alt="" src="../img/icons/logo.png" />
        </nuxt-link>
      </div>
      <div>
        <img class="cart-icon-mobile" alt="" src="../img/icons/supermarket-icon.png"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
  sticky: Boolean,
  },
  data() {
    return {
      text: ''
    }
  },
  // methods: {
  //   onSubmit() {
  //     this.$emit('seatch-text', this.text);
  //     this.$router.push('/search-experience')
  //     this.text = '';
  //   }
  // }
}
</script>
<style>
a {
  color: inherit;
}
.sec-nav {
  display: flex;
  justify-content: space-between;
  width: inherit;
  padding: 0px 12px 0px 12px;
  height: 72px;
  background-color: #ffffff;
  z-index: 200;
  /* margin-bottom: 16px; */
}
.sec-nav-mobile {
  display: flex;
  -webkit-box-pack: justify;
  justify-content: space-between;
  width: inherit;
  padding: 25px 30px 0px 30px;
  height: 72px;
  background-color: #ffffff;
  z-index: 200;
}
.cart-icon-mobile {
    height: 20px;
    margin-bottom: 10px;
}
.logo-box {
    padding-top: 23px;
    padding-left: 21px;
    margin-right: 112px;
}
.nav-items {
  list-style-type: none;
  display: flex;
  justify-content: space-between;
  padding-top: 27px;
  font-weight: 700;
  width: 335px;
}
.search-bar {
  width: 200px;
  height: 40px;
  display: flex;
  /* justify-content: center; */
  border-style: solid;
  border-color: #e3e3e3;
  border-width: thin;
  padding: 0px 5px 0px 5px;
  margin: 16px 20px;
}
.search-bar input {
  border: none;
  outline: none;
  width: 168px;
}
.magnifying-glass {
  width: 15px;
  height: 15px;
  margin: 12px 5px 0px 5px;
}
.bread-crumb {
  height: inherit;
  width: 30px;
}
.crumb-bar {
  height: 2px;
  width: inherit;
  margin-top: 5px;
  background-color: black;
}
.sticky {
  position: fixed;
  top: 0;
  width: 100%;
}
@media (max-width: 1024px) {
  .sec-nav {
    display: none;
  }
}
@media (min-width: 1024px) {
  .sec-nav {
    display: flex;
  }
  .sec-nav-mobile {
    display: none;
  }  
}
</style>