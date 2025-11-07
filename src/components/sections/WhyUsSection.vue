<script setup>
import CheckIcon from '@/assets/icons/check.svg'
import CrossIcon from '@/assets/icons/x.svg'
import Logo from '../ui/Logo.vue'
import SectionHead from '../ui/SectionHead.vue'

const problems = [
  'Low engagement on mobile websites',
  'Generic mobile experience',
  'No developers or tight budgets',
  'Worries about website updates',
  'Unsure before committing',
  'Complex and confusing setup',
  'Outdated limited templates',
  'Hidden extra charges',
]

const solutions = [
  'Send Firebase push notifications to bring',
  'Use our app: configure, click Build; download',
  'Live sync keeps app updated with your site',
  'Paste your URL for a live preview.',
  'Send Firebase push notifications to bring',
  'Simple no-code builder',
  'Modern customizable designs',
  'Clear affordable pricing',
]
</script>

<template>
  <section id="about" class="section why-section">
    <SectionHead
      title="Why Businesses Choose Adaline?"
      discription="The No-Code Website to App Converter That Solves Real Mobile Challenges"
    />

    <div class="details">
      <div class="card">
        <h2>Problem</h2>
        <div class="items">
          <i v-for="p in problems"><CrossIcon /> {{ p }}</i>
        </div>
      </div>

      <div class="card">
        <h2>Solution With ADALINE</h2>
        <div class="items">
          <i v-for="s in solutions"><CheckIcon /> {{ s }}</i>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.why-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2.5rem;

  .details {
    display: flex;
    gap: 1rem;

    @media (max-width: 768px) {
      flex-direction: column;
      width: 100%;
    }

    .card {
      padding: 1rem;
      // border: 1px solid var(--accent-800);
      border-width: 1px;
      border-style: solid;
      border-image: linear-gradient(0, var(--accent-800), var(--accent-700), var(--accent-800)) 1;
      border-radius: 1rem;

      h2 {
        font-size: 1rem;
        padding: 0 1rem;
        margin: 1rem 0;
      }

      .items {
        display: flex;
        flex-direction: column;
        border: 1px solid var(--accent-800);
        border-radius: 0.5rem;
        padding: 1rem 2rem;
        gap: 0.25rem;
        font-size: 0.8rem;
        background: var(--accent-900);
        min-width: 400px;

        i {
          font-style: normal;
          display: flex;
          align-items: center;
          gap: 0.5rem;
        }
      }
    }
  }
}
</style>
