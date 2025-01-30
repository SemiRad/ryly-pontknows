<template>
  <div
    class="flex column justify-center items-center text-center text-h4 text-uppercase font-montserrat text-weight-thin"
  >
    award-winning
    <q-splitter
      v-model="splitterModel"
      horizontal
      class="bg-black q-mb-xl q-mt-md"
      style="height: 1px; width: 40%"
    ></q-splitter>
  </div>

  <div class="row" style="height: fit-content">
    <div class="col">
      <div class="q-pa-md q-ml-xl">
        <q-carousel
          animated
          v-model="slide"
          thumbnails
          infinite
          style="width: 1024px"
          height="682px"
        >
          <q-carousel-slide :name="1" img-src="/img/sandurot-2023.png" />
          <q-carousel-slide :name="2" img-src="/img/catch-a-moment.png" />
          <q-carousel-slide :name="3" img-src="/img/metro-dumaguete.png" />
          <q-carousel-slide :name="4" img-src="/img/all-saints-day.jpg" />
          <q-carousel-slide :name="5" img-src="/img/sandurot-2024.png" />
        </q-carousel>
      </div>
    </div>

    <div class="col-5 flex justify-center items-center">
      <transition name="fade" mode="out-in">
        <div class="column text-center" :key="slide">
          <span class="text-h2 text-weight-bold text-uppercase">{{ dynamicText.title }}</span>
          <span class="text-h5 text-weight-bold text-uppercase">{{ dynamicText.year }}</span>
          <span class="text-h6 text-weight-light" style="line-height: 1">{{
            dynamicText.event
          }}</span>
          <span class="text-h6 text-weight-light" style="line-height: 1">{{
            dynamicText.category
          }}</span>
        </div>
      </transition>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const slide = ref(1)
const splitterModel = ref()

const slideData = [
  {
    title: 'Champion',
    year: '2023',
    event: 'SANDUROT FESTIVAL PHOTOGRAPHY CONTEST',
    category: 'FESTIVAL CONTINGENT',
  },
  {
    title: 'Champion',
    year: '2023',
    event: 'CATCH A MOMENT: A STREET PHOTOGRAPHY PHOTO WALK',
    category: 'photo contest',
  },
  {
    title: 'Champion',
    year: '2024',
    event: 'METRO DUMAGUETE WATER: KAUBAN PHOTOWALK',
    category: 'PHOTO CONTEST',
  },
  {
    title: '3rd place',
    year: '2024',
    event: 'ALL SAINTS DAY',
    category: 'photo contest',
  },
  {
    title: 'Champion',
    year: '2024',
    event: 'SANDUROT FESTIVAL',
    category: 'emotion category',
  },
]

const dynamicText = computed(() => slideData[slide.value - 1])
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-in-out;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
