<script setup lang="ts">
import { DropdownMenuLabel, type DropdownMenuLabelProps } from 'radix-vue'
import { cn } from '@/lib/utils'

const props = defineProps<DropdownMenuLabelProps & { class?: string }>()
</script>

<template>
  <DropdownMenuLabel
    :class="cn('px-2 py-1.5 text-sm font-semibold', props.class)"
    v-bind="props"
  >
    <slot />
  </DropdownMenuLabel>
</template>