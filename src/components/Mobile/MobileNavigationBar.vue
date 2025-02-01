<template>
  <q-layout view="lHh Lpr lFf">
    <!-- Header -->
    <q-header elevated class="bg-black">
      <q-toolbar>
        <q-btn flat round icon="menu" @click="drawerOpen = !drawerOpen" />
      </q-toolbar>
    </q-header>

    <!-- Sidebar Drawer -->
    <q-drawer
      v-model="drawerOpen"
      side="left"
      class="drawer"
      transition-show="slideInLeft"
      transition-hide="slideOutLeft"
    >
      <q-list>
        <q-item clickable @click="navigateTo('#award')">
          <q-item-section><div class="text-body1">AWARD-WINNING</div></q-item-section>
        </q-item>
        <q-item clickable @click="navigateTo('#portrait')">
          <q-item-section><div class="text-body1">PORTRAITS</div></q-item-section>
        </q-item>
        <q-item clickable @click="navigateTo('#festivals')">
          <q-item-section><div class="text-body1">FESTIVALS</div></q-item-section>
        </q-item>
        <q-item clickable @click="navigateTo('#scenes')">
          <q-item-section><div class="text-body1">SCENES</div></q-item-section>
        </q-item>
        <q-item clickable @click="navigateTo('#flavors')">
          <q-item-section><div class="text-body1">FLAVORS</div></q-item-section>
        </q-item>
        <q-item clickable @click="navigateTo('#documentaries')">
          <q-item-section><div class="text-body1">DOCUMENTARIES</div></q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <!-- Main Content -->
    <q-page-container>
      <q-page>
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
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script lang="ts" setup>
import { ref, nextTick } from 'vue'
import AboutContent from '../Mobile/AboutContent.vue'
import AwardContent from '@/components/Mobile/AwardContent.vue'
import PortraitContent from '@/components/Desktop/PortraitContent.vue'
import FestivalContent from '@/components/Desktop/FestivalContent.vue'
import SceneContent from '@/components/Desktop/SceneContent.vue'
import FlavorContent from '@/components/Desktop/FlavorContent.vue'
import DocumentaryContent from '@/components/Desktop/DocumentaryContent.vue'

const drawerOpen = ref(false)

const navigateTo = (sectionId: string) => {
  // Close the drawer first
  drawerOpen.value = false

  // Wait for the drawer transition to finish and then scroll
  nextTick(() => {
    const section = document.querySelector(sectionId)
    if (section) {
      section.scrollIntoView({ behavior: 'smooth' })
    }
  })
}
</script>
