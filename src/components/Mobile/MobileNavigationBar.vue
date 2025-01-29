<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="bg-black">
      <q-toolbar>
        <q-btn flat round icon="menu" @click="drawerOpen = !drawerOpen" />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="drawerOpen"
      side="left"
      class="bg-gray"
      transition-show="slideInLeft"
      transition-hide="slideOutLeft"
    >
      <q-list>
        <q-item clickable to="#award">
          <q-item-section>AWARD-WINNING</q-item-section>
        </q-item>
        <q-item clickable to="#portrait">
          <q-item-section>PORTRAITS</q-item-section>
        </q-item>
        <q-item clickable to="#festivals">
          <q-item-section>FESTIVALS</q-item-section>
        </q-item>
        <q-item clickable to="#scenes">
          <q-item-section>SCENES</q-item-section>
        </q-item>
        <q-item clickable to="#scenes">
          <q-item-section>FLAVORS</q-item-section>
        </q-item>
        <q-item clickable to="#scenes">
          <q-item-section>DOCUMENTARIES</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>
  </q-layout>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const drawerOpen = ref(false)
</script>

<style lang="css" scoped>
body {
  font-family: 'Montserrat', sans-serif;
}

.q-drawer .q-item:hover {
  background-color: #333;
  color: white;
}

.q-drawer {
  transition: transform 0.3s ease-in-out;
}
</style>
