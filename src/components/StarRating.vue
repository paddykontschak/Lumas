<script setup>
import { ref } from 'vue'
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
let updatedScore = null;

const stars = ref({});

const states = ref({
  '1': 'empty',
  '2': 'empty',
  '3': 'empty',
  '4': 'empty',
  '5': 'empty'
})

function setState(n) {
  const statesLength = Object.values(states.value).length;

  for (let index = 1; index <= statesLength; index++) {
    if (index <= n) {
      states.value[index] = 'full';
    } else {
      states.value[index] = 'empty';
    }
  }

  updatedScore = n;
}
</script>

<template>
  <div class="star-rating">
    <span class="category">{{category}}</span>
    <Star
      v-for="n in 5"
      :key="n"
      @click="setState(n)"
      :ref="(el) => (stars[n] = el)"
      :state="states[n]"
    />
    <span class="score">{{updatedScore ?? score}} / 5</span>
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
