<script setup>
const props = defineProps({
  title: String,
  discription: String,
})
</script>

<template>
  <div class="head">
    <h1>{{ title }}</h1>
    <p>{{ discription }}</p>
  </div>
</template>

<style lang="scss" scoped>
.head {
  text-align: center;
  text-transform: uppercase;
  max-width: 500px;
  margin: 0 auto;

  h1 {
    margin-bottom: 1rem;
  }

  p {
    color: var(--text-soft);
  }
}
</style>
