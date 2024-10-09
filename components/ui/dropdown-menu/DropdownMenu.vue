<script setup lang="ts">
import { DropdownMenu as DropdownMenuPrimitive } from 'radix-vue'

defineProps<{
  open?: boolean
}>()

const emit = defineEmits(['update:open'])
</script>

<template>
  <DropdownMenuPrimitive :open="open" @update:open="emit('update:open', $event)">
    <slot />
  </DropdownMenuPrimitive>
</template>