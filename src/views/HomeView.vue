<template>
  <div class="home">
    <!-- component -->
    <div class="bg-gray-100 h-screen">
      <nav class="bg-green-600 px-6 relative shadow-md">
        <div class="flex flex-row justify-between items-center py-2">
          <img src="../assets/logo_uno.gif" class="h-12" alt="">
          <h3 class="font-bold text-3xl text-gray-200 font-sans">{{ nombre }}</h3>
          <div class="group flex flex-col items-center">
            <button class="rounded-lg md:hidden">
              <svg class="h-8 fill-current text-gray-300 font-bold" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 16 16">
                <path fill-rule="evenodd" d="M2.5 12a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5z"/>
              </svg>
            </button>
          </div>
        </div>
      </nav>

      <!-- Radio -->
      <audio controls="controls" id="audio-player" style="display: none">
        <source :src="url" type="audio/ogg" />
      </audio>

      <div class="text-center mt-24">
        <button>
          <svg v-show="!playof" @click="toggleAudio()" class="text-green-600 w-44 h-44" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.752 11.168l-3.197-2.132A1 1 0 0010 9.87v4.263a1 1 0 001.555.832l3.197-2.132a1 1 0 000-1.664z"></path>
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path>
          </svg>
        </button>
        <button>
          <svg v-show="playof" @click="toggleAudio()" class="text-green-600 w-44 h-44" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 9v6m4-6v6m7-3a9 9 0 11-18 0 9 9 0 0118 0z"></path>
          </svg>
        </button>
      </div>
      <!-- End Radio -->
      
      <div class="text-center pt-0 mt-0">
        <img v-if="!playof" src="../assets/frecuencia2.jpg" class="h-28 w-64 inline-block" style="animation-play-state: paused" alt="">
        <img v-else src="../assets/frecuencia2.gif" class="h-28 w-64 inline-block" style="animation-play-state: paused" alt="">
      </div>


    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  data() {
    return {
      nombre: 'Radio uno',
      playof: false,
      url: 'https://stream2.eistreaming.com:10995/;'
    }
  },
  methods: {
    toggleAudio() {
      this.playof = !this.playof;
      var audio = document.getElementById("audio-player");
      if (audio.paused) {
        audio.play();
      } else {
        audio.pause();
      }
    }
  },
  mounted() {
  }
}
</script>
