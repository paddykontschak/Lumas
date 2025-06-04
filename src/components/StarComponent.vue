<script setup>
defineProps([
  'state'
])
</script>

<template>
  <span class="star" v-if="state == 'full'">★</span>
  <span class="star" v-else-if="state == 'empty'">☆</span>
</template>

<style scoped>
.star {
  font-size: 24px;
  vertical-align: middle;
  cursor: pointer;
}
</style>
