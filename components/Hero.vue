<template>
  <div
    class="
      relative
      h-full
      bg-cyan-200
      flex
      justify-center
      items-center
      flex-col
    "
  >
    <h1 class="text-5xl text-center pt-8 pb-4 leading-snug">
      Deine Job<br />website
    </h1>
    <img class="w-full" src="../assets/handshake.svg" />
    <img
      class="absolute -bottom-0 -left-1/2 wave"
      src="../assets/wave-hero.png"
      alt=""
    />
  </div>
</template>

<script>
export default {
  name: 'Hero',
}
</script>

<style lang="postcss" scoped>
.bg-cyan-200 {
  background-color: #e6fffa;
}
.wave {
  max-width: 200%;
  width: 200%;
}
</style>
