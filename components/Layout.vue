<template>
  <div style="position:relative" v-on:scroll.passive="handleScroll">
    <Nav />
    <!-- :searchResults="searchResults" v-on:search-text="searchText" -->
    <SecondaryNav  :sticky="sticky"/>
    <SideNav />
    <slot />
    <Footer />
  </div>
</template>

<script>
import Nav from '~/components/Nav'
import SecondaryNav from '~/components/SecNav'
import SideNav from '~/components/SideNav'
import Footer from '~/components/Footer'

export default {
  components: {
    Nav,
    SecondaryNav,
    SideNav,
    Footer
  },
  // props: ['searchResults'],
    // props: ['searchResults'],
  data() {
    return {
      sticky: false,
      // text: '',
      // searchResults: [],
    }
  },
  methods: {
    //   async searchText(text) {
    //   const config = {
    //   headers: {
    //     Accepts: "application/json"
    //   }
    // };

    // try {
    //   const response = await this.$axios.get(
    //     `/experiences/search?name=${text}`,
    //     config
    //   );

    //   const { data } = response.data;

    //   console.log('res data', data);

    //   this.searchResult = data;
    //   console.log('res result', this.searchResult);
    // } catch (err) {
    //   console.log("search err", err);
    // }
    // },
    handleScroll: function() {
      if (window.scrollY > 28) {
        this.sticky = true
      } else {
        this.sticky = false
      }
    },
  },
  beforeMount () {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  }
}
</script>
