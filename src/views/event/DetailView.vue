<script setup lang="ts">
import { toRefs, onMounted, toRef } from 'vue'
import { type Event } from '@/types'
import { useRoute } from 'vue-router'
import { useMessageStore } from '@/stores/message'

const props = defineProps<{
  event: Event
  id: String
}>()
const { event } = toRefs(props)
const route = useRoute()
const store = useMessageStore()
</script>
<template>
  <div>
  <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
  <p>{{ event.description }}</p>
  <div v-if="store.message" class="flash-message">{{ store.message }}</div>
</div>
</template>
<style scoped>
@keyframes yellofade {
  from {
    background-color: yellow;
  }
  to {
    background-color: transparent;
  }
}

.flash-message {
  animation: yellofade 3s ease-in-out;
  padding: 10px;
  background-color: yellow;
  color: #3c763d;
  border-radius: 4px;
  margin-top: 10px;
}
</style>