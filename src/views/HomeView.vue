<template>
  <div>
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <Home />
    <About />
  </div>
</template>

<script>
import Home from '@/components/Home.vue'
import About from '@/components/About.vue'

export default {
  name: 'HomeView',
  components: {
    Home,
    About
  }
}
</script>
