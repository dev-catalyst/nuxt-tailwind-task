<template>
  <div class="pb-24" @touchstart="touchStart" @touchEndMethod="touchEnd">
    <div
      :class="{
        'h-fill': true,
        'px-6': true,
        'my-8': true,
        flex: true,
        'justify-center': selectedTab === 2,
        'justify-end': selectedTab === 3,
      }"
    >
      <div
        :class="{
          'w-6/12': true,
          'px-7': true,
          'py-2': true,
          'bg-cyan-500': selectedTab === 1,
          'bg-white': selectedTab !== 1,
          'cursor-pointer': true,
          border: true,
          'rounded-l-lg': true,
          'text-white': selectedTab === 1,
          'text-cyan-500': selectedTab !== 1,
          'font-semibold': true,
        }"
        @click="setSelectedTab(1)"
      >
        Arbeitnehmer
      </div>
      <div
        :class="{
          'w-6/12': true,
          'px-7': true,
          'py-2': true,
          'bg-cyan-500': selectedTab === 2,
          'bg-white': selectedTab !== 2,
          'cursor-pointer': true,
          border: true,
          'text-white': selectedTab === 2,
          'text-cyan-500': selectedTab !== 2,
          'font-semibold': true,
        }"
        @click="setSelectedTab(2)"
      >
        Arbeitgeber
      </div>
      <div
        :class="{
          'w-6/12': true,
          'px-7': true,
          'py-2': true,
          'bg-cyan-500': selectedTab === 3,
          'bg-white': selectedTab !== 3,
          'cursor-pointer': true,
          border: true,
          'rounded-r-lg': true,
          'text-white': selectedTab === 3,
          'text-cyan-500': selectedTab !== 3,
          'font-semibold': true,
        }"
        @click="setSelectedTab(3)"
      >
        Temporärbüro
      </div>
    </div>
    <CurrentSteps
      :stepData="selectedTab === 1 ? step1 : selectedTab === 2 ? step2 : step3"
      :selectedTab="selectedTab"
    />
  </div>
</template>

<script>
import CurrentSteps from '../Steps/CurrentSteps.vue'

export default {
  name: 'Steps',
  components: { CurrentSteps },
  data() {
    return {
      selectedTab: 1,
      step1: {
        header: 'Drei einfache Schritte zu deinem neuen Job',
        text1: 'Erstellen dein Lebenslauf',
        text2: 'Erstellen dein Lebenslauf',
        text3: 'Mit nur einem Klick bewerben',
        image1: 'tab1step1.svg',
        image2: 'tab1step2.svg',
        image3: 'tab1step3.svg',
      },
      step2: {
        header: 'Drei einfache Schritte zu deinem neuen Mitarbeiter',
        text1: 'Erstellen dein Unternehmensprofil',
        text2: 'Erstellen ein Jobinserat',
        text3: 'Wähle deinen neuen Mitarbeiter aus',
        image1: 'tab1step1.svg',
        image2: 'tab2step2.svg',
        image3: 'tab2step3.svg',
      },
      step3: {
        header: 'Drei einfache Schritte zur Vermittlung neuer Mitarbeiter',
        text1: 'Erstellen dein Unternehmensprofil',
        text2: 'Erhalte Vermittlungs- angebot von Arbeitgeber',
        text3: 'Vermittlung nach Provision oder Stundenlohn',
        image1: 'tab1step1.svg',
        image2: 'tab3step2.svg',
        image3: 'tab3step3.svg',
      },
    }
  },
  methods: {
    setSelectedTab(value) {
      this.selectedTab = value
    },
    touchStart(touchEvent) {
      if (touchEvent.changedTouches.length !== 1) {
        // We only care if one finger is used
        return
      }
      const posXStart = touchEvent.changedTouches[0].clientX
      addEventListener(
        'touchend',
        (touchEvent) => this.touchEnd(touchEvent, posXStart),
        { once: true }
      )
    },
    touchEnd(touchEvent, posXStart) {
      if (touchEvent.changedTouches.length !== 1) {
        // We only care if one finger is used
        return
      }
      const posXEnd = touchEvent.changedTouches[0].clientX
      if (posXStart < posXEnd) {
        // swipe right
        if (this.selectedTab !== 1) this.selectedTab = this.selectedTab - 1
      } else if (posXStart > posXEnd) {
        // swipe left
        if (this.selectedTab !== 3) this.selectedTab = this.selectedTab + 1
      }
    },
  },
}
</script>

<style lang="postcss" scoped>
.bg-cyan-500 {
  background-color: #81e6d9;
}
.text-cyan-500 {
  color: #319795;
}
</style>
