<script setup>
import { onBeforeMount, onBeforeUnmount, ref } from 'vue'
import Button from './Button.vue'
import Logo from './Logo.vue'

const mobileNavbar = ref(false)

const handleClickOutside = (event) => {
  if (!event.target.classList.contains('mobile-menu-button')) {
    mobileNavbar.value = false
  }
}

onBeforeMount(() => {
  document.addEventListener('click', handleClickOutside)
})

onBeforeUnmount(() => {
  document.removeEventListener('click', handleClickOutside)
})
</script>

<template>
  <header>
    <Logo />

    <nav :class="{ 'mobile-nav': mobileNavbar }">
      <a href="#about">About Us</a>
      <a href="#features">Features</a>
      <a href="#pricing">Pricing</a>
      <a href="#faqs">Questions</a>
    </nav>

    <div class="actions">
      <Button type="secondary">Contact</Button>
      <Button>Create Account</Button>
    </div>

    <button class="mobile-menu-button" @click="mobileNavbar = true">☰</button>
  </header>
</template>

<style lang="scss" scoped>
header {
  display: flex;
  align-items: center;
  gap: 1rem;
  min-height: 60px;
  position: fixed;
  top: 1rem;
  left: 1rem;
  right: 1rem;
  padding: 0 2rem;
  border: 1px solid var(--accent-800);
  border-radius: 25px;
  backdrop-filter: blur(12px);

  nav {
    a {
      padding: 12px 24px;
      transition: all 0.5s ease;
      border-bottom: 1px solid transparent;

      &:hover {
        border-bottom: 1px solid var(--accent-300);
        color: var(--accent-300);
      }
    }

    @media (max-width: 768px) {
      display: none;

      &.mobile-nav {
        display: flex;
        flex-direction: column;
        position: absolute;
        right: 0;
        top: 100%;
        background: var(--accent-900);
        width: 100%;
      }
    }
  }

  .actions {
    margin-left: auto;
    display: flex;
    gap: 0.5rem;
  }

  .mobile-menu-button {
    display: none;
    color: var(--text);
    background: none;
    border: none;
    font-size: 1.3rem;
    cursor: pointer;
    padding: 0 0.5rem;

    @media (max-width: 768px) {
      display: block;
    }
  }
}
</style>
