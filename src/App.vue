<template>
  <HeaderComponent/>

  <RouterView />
</template>

<script>
import { RouterLink, RouterView } from 'vue-router'
import HeaderComponent from './components/HeaderComponent.vue'


export default {
  components: {
    HeaderComponent,
  },

}
</script>

<style scoped>
</style>
