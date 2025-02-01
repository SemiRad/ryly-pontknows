<template>
  <div class="q-my-xl">
    <div
      class="flex column justify-center items-center text-center text-h5 text-uppercase font-montserrat text-weight-thin q-mt-xl"
    >
      <div class="text-weight-bold q-mt-xl">Scenes</div>
      <q-splitter
        v-model="splitterModel"
        horizontal
        class="bg-black q-mb-lg q-mt-md"
        style="height: 1px; width: 40%"
      />
      <div class="q-mb-xl text-h6">Life as we know it</div>
    </div>

    <div class="carousel-wrapper" ref="carouselWrapper">
      <div class="carousel-track" ref="carouselTrack">
        <img
          v-for="(image, index) in images"
          :key="index"
          :src="image"
          :alt="`Slide ${index + 1}`"
        />
        <!-- Cloned images for smooth looping -->
        <img
          v-for="(image, index) in images"
          :key="`clone-${index}`"
          :src="image"
          :alt="`Slide Clone ${index + 1}`"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'

const splitterModel = ref()
const images = [
  '/img/scenes/image (8).png',
  '/img/scenes/image (9).png',
  '/img/scenes/image (10).png',
  '/img/scenes/image (22).png',
  '/img/scenes/image (23).png',
  '/img/scenes/image (24).png',
]

const carouselWrapper = ref<HTMLDivElement | null>(null)
const carouselTrack = ref<HTMLDivElement | null>(null)

onMounted(() => {
  const track = carouselTrack.value

  if (track) {
    let position = 0

    const scrollCarousel = () => {
      position -= 1 // Adjust speed by changing this value
      if (Math.abs(position) >= track.scrollWidth / 2) {
        position = 0 // Reset position seamlessly
      }
      ;(track as HTMLDivElement).style.transform = `translateX(${position}px)`
      requestAnimationFrame(scrollCarousel)
    }

    scrollCarousel()
  }
})
</script>

<style scoped>
.carousel-wrapper {
  overflow: hidden;
  width: 100%;
  margin: auto;
  height: fit-content;
  position: relative;
}

.carousel-track {
  display: flex;
  width: max-content;
  transition: transform 0.1s linear;
}

.carousel-track img {
  object-fit: cover;
  height: 700px;
  margin: 0 20px;
}
</style>
