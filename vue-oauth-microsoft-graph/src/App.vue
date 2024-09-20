<template>
    <div>
      <base-header />
      <HomePage />
      <base-footer />
    </div>
</template>

<script>
import HomePage from './pages/HomePage.vue';
import BaseHeader from './components/base-header.vue';
import BaseFooter from './components/base-footer.vue';
export default {
  name: 'App',
  components: {
    HomePage, BaseHeader, BaseFooter
  },
}
</script>

<style>
/* Add your styles here */
</style>
