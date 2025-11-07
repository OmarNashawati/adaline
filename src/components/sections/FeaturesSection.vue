<script setup>
import SectionHead from '../ui/SectionHead.vue'

const features = [
  {
    title: 'One-Click Website to App',
    subtitle: 'Appilix Dashboard',
    description: 'Turn your existing site into a mobile app instantly, no developers, no delays.',
  },
  {
    title: 'Push Notification that Drive Action',
    subtitle: 'Notification',
    description: 'Send real-time updates to your users and keep them coming back.',
  },
  {
    title: 'Navigation Drawer',
    subtitle: 'Navigation Drawer',
    description:
      'Give users a clean, organized menu that feels a native app. Use a navigation drawer for quick access to improve your app.',
  },
  {
    title: 'Biometric Authentication',
    subtitle: 'Biometric Authentication',
    description: 'Protect sensitive areas of your app with fingerprint or face lock.',
  },
  {
    title: 'Custom Splash Screen',
    subtitle: 'Custom Splash Screen',
    description:
      "Show your logo and brand colors every time the app launches. Includes options like 'Change Status Bar Colors in Dark Mode?'",
  },
]
</script>

<template>
  <section id="features" class="section features-section">
    <SectionHead
      title="Power Features That Make Your App Stand Out"
      discription="ADALINE offers adward features and a no-code way to turn your website into a native mobile app."
    />

    <div class="cards-warpper">
      <div class="card" v-for="feature in features">
        <h3>{{ feature.title }}</h3>
        <p>{{ feature.description }}</p>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.features-section {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  .cards-warpper {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;

    @media (max-width: 768px) {
      grid-template-columns: repeat(2, 1fr);
    }

    .card {
      border: 1px solid var(--accent-800);
      border-radius: 1rem;
      padding: 1rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
  }
}
</style>
