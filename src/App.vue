<template>
  <div id="app">
    <transition name="fade" mode="out-in">
      <div class="">
      <router-view></router-view>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
  #app {
  }
  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s ease-out;
  }
  .fade-enter, .fade-leave {
    opacity: 0;
  }
</style>
