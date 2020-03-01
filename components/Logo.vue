<template>
  <div class="test-logo">
    <img alt="" src="../img/icons/logo.png" />
  </div>
</template>
<script>
export default {

}
</script>
<style>
.test-logo {
  animation: 1s appear;
  height: 39px;
  margin-top: 80px;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
