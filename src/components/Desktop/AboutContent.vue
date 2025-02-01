<template>
  <div class="col q-my-xl flex fade-in" style="height: 90vh">
    <div class="col text-center font-poppins text-h3">
      <div class="text-h1" style="text-transform: uppercase; font-weight: 500">Ryly Pontino</div>
      <div class="text-h6" style="font-weight: 300">freezing a moment</div>
      <div class="row justify-between items-center q-mt-xl">
        <div class="col-5">
          <img src="/img/ryly.png" class="profile-img fade-in" />
        </div>
        <div class="col-7 q-pr-xl">
          <div class="flex column">
            <div class="text-h5 text-uppercase text-weight-regular text-left fade-in">about me</div>
            <q-splitter
              v-model="splitterModel"
              horizontal
              class="bg-black q-my-md fade-in"
              style="height: 1px; width: 100%"
            />
            <div class="text-weight-regular text-body1 text-left">
              <div class="q-my-md fade-in">
                I am a freelance photographer passionate about capturing the beauty and essence of
                life’s moments. With a versatile style that spans documentary, street, portrait,
                food, and event photography, I specialize in telling authentic stories through my
                lens.
              </div>
              <div class="q-my-md fade-in">
                My work is all about candid moments, vibrant details, and the unique personalities
                that make every story special. Whether it’s the energy of a bustling event or the
                quiet charm of everyday life, I’m dedicated to creating images that evoke emotion
                and leave a lasting impression.
              </div>
              <div class="q-my-md fade-in">
                Let’s bring your vision to life and turn fleeting moments into timeless memories.
              </div>
              <div class="q-my-md fade-in">
                <a href="https://www.facebook.com/ryly.pontino.22" target="_blank">
                  <i
                    class="fab fa-facebook q-mr-md q-mt-md"
                    style="font-size: 3rem; color: black"
                  ></i>
                </a>
                <a href="https://www.instagram.com/rylyponts/" target="_blank">
                  <i class="fab fa-instagram" style="font-size: 3rem; color: black"></i>
                </a>
              </div>
            </div>
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
.text-h1,
.text-h6,
.profile-img,
.text-h5,
.text-body1,
.fab {
  animation: fadeInOffset 1s forwards;
}

.text-h1 {
  animation-delay: 0.5s;
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
  animation-delay: 1.2s;
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
