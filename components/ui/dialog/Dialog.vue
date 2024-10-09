<script setup lang="ts">
import { Dialog as DialogPrimitive } from 'radix-vue'
import { computed } from 'vue'

const props = defineProps<{
  open?: boolean
}>()

const emit = defineEmits(['update:open'])

const dialogOpen = computed({
  get: () => props.open,
  set: (value) => emit('update:open', value),
})
</script>

<template>
  <DialogPrimitive :open="dialogOpen" @update:open="dialogOpen = $event">
    <slot />
  </DialogPrimitive>
</template>