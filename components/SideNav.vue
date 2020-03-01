<template>
    <div class="sidenav-container">
        <div v-if="toggleSidebar" class="backdrop" @click="$store.dispatch('nav/toggleSidebar')"></div>
        <transition name="slide-side">
            <div v-if="toggleSidebar" class="sidenav">
                <div>
                  <div class="side-nav-item">
                    <div>
                      <img class="mobile-user-nav-icon" alt="" src="../img/icons/user-icon.png" />
                      My Account
                    </div>
                    <div>
                      <img alt="" src="../img/icons/next-3.png" />
                    </div>
                  </div>
                  <hr />
                  <nuxt-link to="/" exact>
                    <div class="side-nav-item item-menu">
                      Home
                      <div>
                        <img alt="" src="../img/icons/next-3.png" />
                      </div>
                    </div>
                  </nuxt-link>
                  <hr />
                  <div class="side-nav-item item-menu">
                    Dining
                    <div>
                      <img alt="" src="../img/icons/next-3.png" />
                    </div>
                  </div>
                  <hr />
                  <div class="side-nav-item item-menu">
                    Adventure
                    <div>
                      <img alt="" src="../img/icons/next-3.png" />
                    </div>
                  </div>
                  <hr />
                </div>
            </div>
        </transition>

    </div>
</template>

<script>
    export default {
        computed: {
            toggleSidebar() {
                return this.$store.getters['nav/toggleSidebar']
            }
        }
    }
</script>


<style scoped>
.mobile-user-nav-icon {
  height: 14px;
}
hr {
    margin: inherit;
}
img {
    margin-right: 10px;
}
.sidenav-container {
  height: 100%;
  width: 100%;
}
.sidenav {
  height: 100%;
  width: 80%;
  background-color: white;
  z-index: 10000;
  position: fixed;
  top: 0;
  left: 0;
  box-sizing: border-box;
  /* padding: 30px; */
}
.side-nav-item {
  height: 60px;
  padding: 19px 5px 0px 25px;
  display: -webkit-box;
  display: flex;
  -webkit-box-pack: justify;
  justify-content: space-between;
  font-size: 14px;
}
.item-menu {
  background-color: #f8f8f8;
}
.backdrop {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  z-index: 1000;
  position: fixed;
  top: 0;
  left: 0;
}
.slide-side-enter-active,
.slide-side-leave-active {
  transition: all 0.3s ease-out;
}
.slide-side-enter,
.slide-side-leave-to {
  transform: translateX(-100%);
}
</style>