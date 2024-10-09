<template>
  <Dialog v-model:open="modelValue" @update:open="$emit('update:show', $event)">
    <DialogContent class="sm:max-w-[425px]">
      <DialogHeader>
        <DialogTitle>Feedback</DialogTitle>
        <DialogDescription>
          Please share your thoughts on the "Gristmas Lights" holiday light show.
        </DialogDescription>
      </DialogHeader>
      <form @submit.prevent="submitFeedback">
        <div class="grid gap-4 py-4">
          <div class="grid grid-cols-4 items-center gap-4">
            <Label for="likes" class="text-right">Likes</Label>
            <Textarea id="likes" v-model="likes" placeholder="What do you like about the show?" class="col-span-3" />
          </div>
          <div class="grid grid-cols-4 items-center gap-4">
            <Label for="dislikes" class="text-right">Dislikes</Label>
            <Textarea id="dislikes" v-model="dislikes" placeholder="What don't you like about the show?" class="col-span-3" />
          </div>
        </div>
        <DialogFooter>
          <Button type="submit">Submit Feedback</Button>
        </DialogFooter>
      </form>
    </DialogContent>
  </Dialog>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import { Dialog, DialogContent, DialogDescription, DialogFooter, DialogHeader, DialogTitle } from '@/components/ui/dialog'
import { Label } from '@/components/ui/label'
import { Textarea } from '@/components/ui/textarea'
import { Button } from '@/components/ui/button'

const props = defineProps<{ show: boolean }>()
const emit = defineEmits(['update:show'])

const modelValue = computed({
  get: () => props.show,
  set: (value) => emit('update:show', value)
})

const likes = ref('')
const dislikes = ref('')

const submitFeedback = () => {
  console.log('Feedback submitted:', { likes: likes.value, dislikes: dislikes.value })
  likes.value = ''
  dislikes.value = ''
  emit('update:show', false)
}
</script>