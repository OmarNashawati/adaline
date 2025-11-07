<script setup>
import ArrowUpIcon from '@/assets/icons/arrow-up.svg'
import Button from '../ui/Button.vue'
</script>

<template>
  <div class="hero-section section">
    <div class="head">
      <span>No Code App Builder</span>
      <h1>Convert Your Website to App Without Code</h1>
      <p>Convert your website to an app with a no-code app builder-fast and easy</p>
    </div>

    <div class="url-input-wrapper">
      <textarea placeholder="Enter your website URL..."></textarea>
      <div class="actions">
        <Button>ISO</Button>
        <Button>Android</Button>
        <Button><ArrowUpIcon class="icon" /></Button>
      </div>
    </div>

    <p class="note"><b>Upgrade</b> to unlock all of ADALINE features & more creadits</p>
  </div>
</template>

<style lang="scss" scoped>
.hero-section {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding-top: 100px;

  .head {
    max-width: 800px;
    display: flex;
    align-items: center;
    flex-direction: column;
    gap: 1rem;
    margin-bottom: 3rem;

    span {
      padding: 12px;
      text-transform: uppercase;
      background: linear-gradient(0, var(--accent-700), var(--accent-900));
      border-radius: 0.25rem;
      width: fit-content;
    }

    h1 {
      font-weight: 900;
      font-size: 3rem;
      text-transform: uppercase;
      @media (max-width: 768px) {
        font-size: 2rem;
      }
    }

    p {
      color: var(--text-soft);
    }
  }

  .url-input-wrapper {
    padding: 1rem;
    border-radius: 1rem;
    background: linear-gradient(0, var(--accent-600), var(--accent-700));
    min-width: 500px;
    aspect-ratio: 10/4;
    display: flex;
    flex-direction: column;
    margin-bottom: 1rem;
    box-shadow:
    /* Inner dark shadow for depth */
      inset 0 0 10px rgba(0, 0, 0, 0.7),
      /* The main, soft, bright glow */ 0 0 25px 5px rgba(0, 255, 255, 0.6),
      /* Cyan glow */ /* A stronger, tighter glow layer */ 0 0 10px 1px rgba(0, 255, 255, 0.8);

    @media (max-width: 768px) {
      min-width: 100%;
    }

    textarea {
      background: none;
      outline: none;
      border: none;
      font-size: 1rem;
      padding: 12px 0;
      color: var(--text);
      width: 100%;
      flex: 1;
      resize: none;

      &::placeholder {
        color: var(--placeholder);
      }
    }

    .actions {
      display: flex;
      gap: 0.5rem;
      margin-top: auto;

      button {
        .icon {
          width: 15px;
          height: 15px;
        }
      }

      button:last-child {
        margin-left: auto;
        aspect-ratio: 1/1;
        padding: 3px;
      }
    }
  }

  .note {
    font-size: 0.8rem;
  }
}
</style>
