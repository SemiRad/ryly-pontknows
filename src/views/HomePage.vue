<template>
  <div v-if="isLargeScreen">
    <Navbar />
    <AboutContent />
    <div id="award">
      <AwardContent />
    </div>
  </div>
  <div v-else>
    <MobileNavbar />
    <AboutContent />
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import Navbar from '@/components/Desktop/NavigationBar.vue'
import MobileNavbar from '@/components/Mobile/MobileNavigationBar.vue'
import AboutContent from '@/components/Desktop/AboutContent.vue'
import AwardContent from '@/components/Desktop/AwardContent.vue'

const isLargeScreen = ref(window.innerWidth >= 768)

const checkScreenSize = () => {
  isLargeScreen.value = window.innerWidth >= 768
}

onMounted(() => {
  window.addEventListener('resize', checkScreenSize)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', checkScreenSize)
})
</script>
