<script setup>
import Rating from './components/RatingComponent.vue'

// We create 1 component for the whole rating element,
// so that we can reuse it on all websites with the preferred
// categories

// Inside the RatingComponent we have a StarRating component
// for each of our categories, with a name for the category
// and the score

// A StarRating component displays the name, the score, and 5
// stars, which themselves are reusable components, too.

// The actual logic for the rating happens in that StarRating
// component.

// This way we can reuse every aspect of the components.
// Want only 1 category? Directly import StarRating
// Want only 4 stars? For production that's something that we
// would need to adjust, but a single star can be used in a
// different component, e.g. as button to open a popup that
// shows the rating component, or as template for a favorite
// button.

// Another thing that would have to be changed for production
// is WCAG 2.2 conform contrast colors. For this task I
// took what `npm create vue@latest` gave me by default.

</script>

<template>
    <a class="credit" href="https://github.com/paddykontschak/Lumas">See the code here</a>
    <Rating />
</template>

<style scoped>

</style>
