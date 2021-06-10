<template>
  <div>
    <h3 class="pt-4 px-6 text-2xl text-center">{{ stepData.header }}</h3>
    <div class="pb-4 -m-4">
      <img
        class="w-7/12 ml-auto mr-12 transform translate-y-1/4"
        :src="require('@/assets/' + stepData.image1 + '')"
      />
      <div class="flex justify-start items-end">
        <span class="text-9xl text-gray-500 ml-4">1.</span>
        <p class="text-gray-500 w-7/12 pb-4 ml-6 mr-4">{{ stepData.text1 }}</p>
      </div>
    </div>
    <div class="pt-12 pb-16 relative bg-cyan-200">
      <div class="flex justify-start items-end">
        <span class="text-9xl text-gray-500 ml-8">2.</span>
        <p class="text-gray-500 w-7/12 pb-4 ml-6 mr-4">{{ stepData.text2 }}</p>
      </div>
      <img
        :class="{
          'w-7/12': selectedTab === 1,
          'w-9/12': selectedTab === 2,
          'w-7/12': selectedTab === 3,
          'ml-auto': true,
          'mt-4': selectedTab === 1,
          'mx-auto': selectedTab !== 3,
          'mr-6': selectedTab === 3,
          transform: selectedTab !== 3,
          '-translate-y-8': selectedTab === 2,
          'translate-x-2': selectedTab === 1,
        }"
        :src="require('@/assets/' + stepData.image2 + '')"
      />
      <img
        class="absolute -top-0 h-12 wave"
        src="../../assets/wave-top.png"
        alt=""
      />
      <img
        class="absolute bottom-0 wave"
        src="../../assets/wave-hero.png"
        alt=""
      />
    </div>
    <div class="pb-8 -m-4">
      <div class="flex justify-start items-center">
        <span class="text-9xl text-gray-500 ml-12">3.</span>
        <p class="text-gray-500 w-7/12 ml-6 mr-4 transform translate-y-3">
          {{ stepData.text3 }}
        </p>
      </div>
      <img
        :class="{
          'w-8/12': true,
          'ml-auto': true,
          'mt-4': selectedTab !== 1,
          'mr-4': selectedTab === 1,
          'mx-auto': selectedTab !== 1,
          transform: selectedTab === 1,
          '-translate-y-6': selectedTab === 1,
        }"
        :src="require('@/assets/' + stepData.image3 + '')"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'CurrentSteps',
  props: {
    stepData: Object,
    selectedTab: Number,
  },
}
</script>

<style lang="postcss" scoped>
.bg-cyan-200 {
  background-color: #e6fffa;
}
.wave {
  max-width: 150%;
  width: 150%;
}
</style>
