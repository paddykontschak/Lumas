<script setup>
import Star from './StarComponent.vue'
defineProps({
  category: {
    type: String,
    required: true,
  },
  score: {
    type: Number,
    required: true,
  },
})
</script>

<template>
  <div class="star-rating">
    <span class="category">{{category}}</span>
    <Star
      v-for="n in 5"
      :key="n"
    />
    <span class="score">{{score}} / 5</span>
  </div>
</template>

<style scoped>
.category {
  display: block;
}

.score {
  padding: 0 15px;
}
</style>
