<template>
  <div class="min-h-screen relative flex items-center justify-center">
    <div
      class="absolute top-0 w-full h-full bg-forest bg-center bg-cover z-0 bg-overlay" />
    <div
      class="flex flex-col md:flex-row md:space-x-10 z-10 items-center px-2 md:px-0">
      <img
        src="./assets/images/vontage-logo.svg"
        class="-mt-20 md:mt-0 w-[160px] md:w-[250px] logo drop-shadow-[0_4px_4px_#000000]" />
      <div
        class="flex flex-col space-y-4 md:space-y-6 px-8 md:px-0 items-center text-white relative">
        <div
          class="text-[#ff0000] font-oleoscript text-8xl md:text-9xl drop-shadow-[0_4px_4px_#000000] leading-tight md:leading-none title">
          Vontage
        </div>
        <div
          class="text-white/90 font-orbitron tracking-wider text-[18px] md:text-[28px] drop-shadow-[0_4px_4px_#000000] subtitle text-center">
          Design, Marketing e Engenharia Digital
        </div>
        <div
          class="absolute bottom-[-60px] md:bottom-[-80px] right-0 font-billiondreams text-[#FBFF48] text-[35px] md:text-[50px] tracking-wide rotate-[-12deg] drop-shadow-[0_4px_4px_#000000] commingsoon">
          Brevemente...
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
const timeline = gsap.timeline()

const fadeOut = () => {
  // timeline.play(0)

  timeline.fromTo(
    '.bg-overlay',
    { filter: 'brightness(0.9)' },
    { filter: 'brightness(0.4)', duration: 0.5, ease: 'power1.out' },
    '<0.5'
  )

  timeline.fromTo(
    '.title',
    { opacity: 0, x: '100%' },
    { opacity: 1, x: 0, duration: 1 },
    '<0.5'
  )

  timeline.fromTo(
    '.logo',
    { opacity: 0, scale: 0 },
    { opacity: 1, scale: 1, duration: 0.5 },
    '<0.5'
  )

  timeline.fromTo(
    '.subtitle',
    { opacity: 0, y: '100%' },
    { opacity: 1, y: 0 },
    '<0.5'
  )
  timeline.fromTo(
    '.commingsoon',
    { opacity: 0 },
    { opacity: 1, duration: 1 },
    '<0.5'
  )
}

onMounted(() => {
  fadeOut()
})
</script>
