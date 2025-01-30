<template>
  <div class="row">
    <div class="col bg-black flex justify-center items-center" style="height: 15vh; color: white">
      <a href="#award" class="text-h5 font-montserrat uppercase q-mx-md">award-winning</a>
      <q-splitter v-model="splitterModel" vertical style="height: 30px" />
      <a href="#portrait" class="text-h5 font-montserrat uppercase q-mx-md">portrait</a>
      <q-splitter v-model="splitterModel" vertical style="height: 30px" />
      <a href="#festivals" class="text-h5 font-montserrat uppercase q-mx-md">festivals</a>
      <q-splitter v-model="splitterModel" vertical style="height: 30px" />
      <a href="#scenes" class="text-h5 font-montserrat uppercase q-mx-md">scenes</a>
      <q-splitter v-model="splitterModel" vertical style="height: 30px" />
      <a href="#scenes" class="text-h5 font-montserrat uppercase q-mx-md">flavors</a>
      <q-splitter v-model="splitterModel" vertical style="height: 30px" />
      <a href="#scenes" class="text-h5 font-montserrat uppercase q-mx-md">documentaries</a>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const splitterModel = ref()
</script>

<style lang="css" scoped>
.font-montserrat {
  font-family: 'Montserrat', sans-serif;
}

a {
  text-transform: uppercase;
  text-decoration: none;
  color: white;
  transition: all 0.3s ease;
}

.q-splitter {
  margin: 0 25px;
  background-color: white;
}

a:hover {
  transform: scale(1.1);
  text-shadow: 0 0 5px white;
}
</style>
