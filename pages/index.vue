<template>
  <div class="p-t-4 p-b-4 w-full h-full overflow-x-hidden">
    <Hero />
    <Steps />
  </div>
</template>

<script>
import Hero from '../components/Hero.vue'
import Steps from '../components/Steps/Steps.vue'

export default {
  components: { Hero, Steps },
}
</script>

<style scoped>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
* {
  font-family: 'Lato', sans-serif;
}
</style>
