<template>
  <div class="max-w-md h-screen relative mx-auto">
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'
export default {
  components: { Header, Footer },
}
</script>
