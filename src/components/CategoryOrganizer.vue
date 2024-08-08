<script setup lang="ts">
import { defineProps } from 'vue'
import Event from '@/types/Event'

defineProps<{
  event: Event
}>()
</script>

<template>
  <div class="category-organizer">
    <div class="event-card">
      <h2>{{ event.category }}</h2>
      <h2>{{ event.organizer }}</h2>
    </div>
  </div>
</template>

<style scoped>
.category-organizer {
  display: flex;
  justify-content: flex-end;
  font-size: 16px;
  gap: 10px;
  text-align: right;
}
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
.category-organizer span {
  text-align: right;
}
</style>
