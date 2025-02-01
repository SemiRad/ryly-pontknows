<template>
  <div class="col q-my-xl flex fade-in" style="height: fit-content">
    <div class="col text-center font-poppins text-h3">
      <div class="text-h2" style="text-transform: uppercase; font-weight: 500">Ryly Pontino</div>
      <div class="text-h6" style="font-weight: 300">freezing a moment</div>
      <div class="col-5 q-py-xl">
        <img src="/img/ryly.png" class="profile-img" />
      </div>
      <div class="col text-center q-mx-xl">
        <div class="text-h5 text-uppercase text-weight-regular text-center">about me</div>
        <q-splitter
          v-model="splitterModel"
          horizontal
          class="bg-black q-my-md"
          style="height: 1px; width: 100%"
        />
        <div class="text-weight-regular text-body1 text-left">
          <div class="q-my-md">
            I am a freelance photographer passionate about capturing the beauty and essence of
            life’s moments. With a versatile style that spans documentary, street, portrait, food,
            and event photography, I specialize in telling authentic stories through my lens.
          </div>
          <div class="q-my-md">
            My work is all about candid moments, vibrant details, and the unique personalities that
            make every story special. Whether it’s the energy of a bustling event or the quiet charm
            of everyday life, I’m dedicated to creating images that evoke emotion and leave a
            lasting impression.
          </div>
          <div class="q-my-md">
            Let’s bring your vision to life and turn fleeting moments into timeless memories.
          </div>
          <div class="q-my-md items-center justify-center row" style="gap: 20px">
            <a href="https://www.facebook.com/ryly.pontino.22" target="_blank">
              <i class="fab fa-facebook" style="font-size: 3rem; color: black"></i>
            </a>
            <a href="https://www.instagram.com/rylyponts/" target="_blank">
              <i class="fab fa-instagram" style="font-size: 3rem; color: black"></i>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const splitterModel = ref()
</script>

<style lang="css" scoped>
/* Fade-in effect with an offset */
.fade-in {
  opacity: 0;
  transform: translateY(30px); /* Offset the element lower initially */
  animation: fadeInOffset 1s forwards;
}

@keyframes fadeInOffset {
  to {
    opacity: 1;
    transform: translateY(0); /* Element returns to its original position */
  }
}

/* Staggered effect for the child elements */
.text-h2,
.text-h6,
.profile-img,
.text-h5,
.text-body1 {
  animation: fadeInOffset 2s forwards;
}

.text-h2 {
  animation-delay: 0.2s;
}

.text-h6 {
  animation-delay: 0.4s;
}

.profile-img {
  width: 50%;
  height: 100%;
  border-radius: 100%;
  animation-delay: 0.6s;
}

.text-h5 {
  animation-delay: 0.8s;
}

.text-body1 {
  animation-delay: 1s;
}

.fab {
  transition: all 0.3s ease;
}

.fab:hover {
  cursor: pointer;
  transform: scale(1.1);
  text-shadow: 0 0 5px white;
}
</style>
