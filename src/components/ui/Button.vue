<script setup>
const props = defineProps({
  type: {
    type: String,
    validator: (value) => ['primary', 'secondary'].includes(value),
    default: 'primary',
  },
})
</script>

<template>
  <button :class="type">
    <slot></slot>
  </button>
</template>

<style lang="scss" scoped>
button {
  display: block;
  // border: 1px solid var(--text);
  border: none;
  color: var(--text);
  padding: 8px 12px;
  border-radius: 0.25rem;
  font-size: 0.9rem;
  cursor: pointer;

  &:hover {
    box-shadow:
    /* Inner top shadow for a 'raised'/glossy look */
      inset 0 1px 0 rgba(255, 255, 255, 0.4),
      /* Main neon outer glow */ 0 0 8px 1px rgba(0, 255, 255, 0.7);
  }

  &.primary {
    background: var(--accent-300);
  }

  &.secondary {
    background: var(--accent-700);
  }
}
</style>
