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

  <main>
    <div class="container py-5">
      <router-view></router-view>
    </div>
  </main>
</template>

<style lang="scss">
@use './styles/general.scss' as *;
</style>
