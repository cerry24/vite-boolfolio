<script>
import AppHeader from './components/AppHeader.vue';

export default {
  components: {
    AppHeader
  }
}
</script>

<template>
  <AppHeader />

  <main class="container py-3">
    <router-view></router-view>
  </main>
</template>

<style lang="scss">
@use './styles/general.scss' as *;
</style>
