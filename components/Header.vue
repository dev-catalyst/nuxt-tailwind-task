<template>
  <div
    class="
      absolute
      z-10
      top-0
      bg-white
      w-full
      border-b border-grey-600 border-opacity-50
      rounded-b-2xl
      shadow-xl
    "
  >
    <div
      class="
        bg-gradient-to-r
        from-green-600
        via-blue-500
        to-blue-500
        h-2
        w-full
      "
    ></div>
    <div class="flex justify-center items-center">
      <span
        class="
          w-11/12
          p-2
          mt-4
          mb-4
          flex
          justify-end
          text-green-600
          font-sm font-medium
          cursor-pointer
        "
      >
        Login
      </span>
    </div>
  </div>
</template>

<style lang="postcss" scoped>
.shadow-xl {
  box-shadow: 0px 2px 8px #888888;
}

.to-blue-500 {
  --tw-gradient-to: #3182ce;
}
.to-green-600 {
  --tw-gradient-to: #319795;
}
.text-green-600 {
  color: #319795;
}
</style>
