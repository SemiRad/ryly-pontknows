<template>
  <div>
    <Navbar v-if="isLargeScreen" />
    <MobileNavbar v-else />
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import Navbar from '@/components/Desktop/NavigationBar.vue'
import MobileNavbar from '@/components/Mobile/MobileNavigationBar.vue'

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
