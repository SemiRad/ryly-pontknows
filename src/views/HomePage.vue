<template>
  <!-- Responsive Navbar -->
  <div v-if="isLargeScreen">
    <Navbar style="position: sticky" />
    <AboutContent />
    <div id="award">
      <AwardContent />
    </div>
    <div id="portrait">
      <PortraitContent />
    </div>
    <div id="festivals">
      <FestivalContent />
    </div>
    <div id="scenes">
      <SceneContent />
    </div>
    <div id="flavors">
      <FlavorContent />
    </div>
    <div id="documentaries">
      <DocumentaryContent />
    </div>
  </div>
  <div v-else>
    <MobileNavbar />
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import Navbar from '@/components/Desktop/NavigationBar.vue'
import MobileNavbar from '@/components/Mobile/MobileNavigationBar.vue'

// Shared Content Components
import AboutContent from '@/components/Desktop/AboutContent.vue'
import AwardContent from '@/components/Desktop/AwardContent.vue'
import PortraitContent from '@/components/Desktop/PortraitContent.vue'
import FestivalContent from '@/components/Desktop/FestivalContent.vue'
import SceneContent from '@/components/Desktop/SceneContent.vue'
import FlavorContent from '@/components/Desktop/FlavorContent.vue'
import DocumentaryContent from '@/components/Desktop/DocumentaryContent.vue'

// Detect Screen Size
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
