<script setup>
const props = defineProps(['close'])
</script>

<template>
  <div v-if="close" class="modal">
    <p class="headline">Design By</p>
    <a
      class="link"
      href="https://dribbble.com/shots/26704397-Adaline-No-Code-App-Builder-Landing-Page"
      >Ofspace UX/UI</a
    >
    <button @click="$emit('close')">Close</button>
  </div>
</template>

<style lang="scss" scoped>
.modal {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: white;
  color: #121212;
  padding: 1rem;
  min-width: 220px;
  border-radius: 0.25rem;

  .headline {
    font-weight: 600;
  }

  .link {
    display: block;
    color: #121212;
    margin-bottom: 1rem;

    &:hover {
      text-decoration: underline;
    }
  }

  button {
    display: block;
    padding: 8px 16px;
    background-color: #121212;
    color: white;
    border: 0;
    border-radius: 25px;
    margin-left: auto;
    cursor: pointer;

    &:hover {
      background-color: #12121270;
    }
  }
}
</style>
