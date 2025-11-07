<script setup></script>

<template>
  <div class="modal">
    <p class="headline">Design By</p>
    <a
      class="link"
      href="https://dribbble.com/shots/26704397-Adaline-No-Code-App-Builder-Landing-Page"
      >Ofspace UX/UI</a
    >
    <button>Close</button>
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
  min-width: 180px;
  border-radius: 0.25rem;

  .headline {
    font-weight: 600;
  }

  .link {
    display: block;
    color: #121212;
    margin: 12px 0;

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
    cursor: pointer;

    &:hover {
      background-color: #12121270;
    }
  }
}
</style>
