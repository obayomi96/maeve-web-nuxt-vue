<template>
  <div class="notification">
    {{ message }}
  </div>
</template>

<script>
export default {
  name: 'Notification',
  props: ['message']
}
</script>

<style scoped>
  .notification {
    background: #000;
    color: #fff;
  }
</style>