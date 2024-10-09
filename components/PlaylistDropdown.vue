<template>
  <DropdownMenu v-model:open="isOpen">
    <DropdownMenuTrigger class="p-2 hover:bg-white/10 rounded-full transition">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" />
      </svg>
    </DropdownMenuTrigger>
    <DropdownMenuContent class="w-56 bg-gray-800 text-white border-gray-700">
      <DropdownMenuLabel class="font-bold">Playlist</DropdownMenuLabel>
      <DropdownMenuSeparator class="bg-gray-700" />
      <DropdownMenuItem v-for="(item, index) in playlistItems" :key="index" class="focus:bg-gray-700">
        {{ item }}
      </DropdownMenuItem>
    </DropdownMenuContent>
  </DropdownMenu>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import {
  DropdownMenu,
  DropdownMenuTrigger,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
} from '@/components/ui/dropdown-menu'

const isOpen = ref(false)

const playlistItems = [
  'Song 1',
  'Song 2',
  'Song 3',
  'Song 4',
  'Song 5',
  'Song 6',
  'Song 7',
  'Song 8',
  'Song 9',
  'Song 10',
]
</script>