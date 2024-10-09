<template>
  <div class="h-screen w-screen overflow-hidden relative">
    <img
      src="https://get.wallhere.com/photo/night-branch-Christmas-Tree-Christmas-bokeh-holiday-fir-Denmark-light-tree-xmas-christmastree-julgran-julgranskulor-jul-danmark-nightphotography-tivoli-natt-exif-model-canoneos760d-geocountry-camera-make-canon-geocity-camera-model-canoneos760d-geostate-geolocation-exif-make-canon-exif-focallength-50mm-exif-isospeed-5000-exif-lens-ef50mmf18stm-exif-aperture-20-kopenhavn-k-penhamncopenhagen-ornamnents-christmas-decoration-macro-photography-458758.jpg"
      alt="Background"
      class="absolute inset-0 w-full h-full object-cover"
    />
    <div class="absolute inset-0 flex flex-col">
      <header class="p-4 text-white flex justify-between items-center">
        <h1 class="text-2xl font-bold">Gristmas Lights</h1>
        <Button @click="showModal = true">Feedback</Button>
      </header>
      <main class="flex-grow"></main>
      <footer class="p-4 bg-gradient-to-t from-black/60 to-transparent">
        <div class="max-w-screen-xl mx-auto">
          <div class="flex flex-col space-y-2 mb-4">
            <div class="w-full bg-gray-600 rounded-full h-1">
              <div class="bg-white h-1 rounded-full w-1/3"></div>
            </div>
            <div class="flex justify-between items-center w-full text-white text-sm">
              <span>1:23</span>
              <span>3:45</span>
            </div>
          </div>
          <div class="flex justify-between items-center text-white">
            <div class="w-1/3">
              <PlaylistDropdown />
            </div>
            <div class="w-1/3 flex justify-center items-center space-x-6">
              <button class="p-2 hover:bg-white/10 rounded-full transition">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                </svg>
              </button>
              <button class="p-2 hover:bg-white/10 rounded-full transition">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-12 w-12" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.752 11.168l-3.197-2.132A1 1 0 0010 9.87v4.263a1 1 0 001.555.832l3.197-2.132a1 1 0 000-1.664z" />
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </button>
              <button class="p-2 hover:bg-white/10 rounded-full transition">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                </svg>
              </button>
            </div>
            <div class="w-1/3 text-right">
              <span class="font-semibold">Song Title</span>
              <span class="mx-2">•</span>
              <span class="text-gray-300">Artist Name</span>
            </div>
          </div>
        </div>
      </footer>
    </div>
    <FeedbackModal v-model:show="showModal" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import PlaylistDropdown from './components/PlaylistDropdown.vue'
import FeedbackModal from './components/FeedbackModal.vue'
import { Button } from './components/ui/button'

const showModal = ref(false)
</script>