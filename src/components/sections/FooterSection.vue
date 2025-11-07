<script setup>
import Logo from '../ui/Logo.vue'

const footerSection = {
  companyInfo: {
    title: 'Appilix - Web to App Converter',
    tagline:
      'Turn your website into a powerful mobile app instantly. No coding, no developers, just results.',
  },
  navigationLinks: [
    {
      title: 'Product',
      links: ['Features', 'Pricing', 'Live Demo', 'Case Studies'],
    },
    {
      title: 'Support',
      links: ['Contact Us', 'Help Center', 'FAQs', 'Refund Policy'],
    },
    {
      title: 'Legal',
      links: ['Terms & Conditions', 'Privacy Policy', 'Sitemap'],
    },
  ],
  copyright: '© 2025 Appilix. All rights reserved.',
}
</script>

<template>
  <footer class="section">
    <div class="brand-wrapper">
      <Logo />
      <p>{{ footerSection.companyInfo.tagline }}</p>
    </div>

    <nav class="links">
      <div v-for="navLink of footerSection.navigationLinks" class="links-group">
        <h3>{{ navLink.title }}</h3>
        <a href="" v-for="link in navLink.links">{{ link }}</a>
      </div>
    </nav>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  display: flex;
  gap: 2rem;
  border-top: 2px solid var(--accent-800);

  @media (max-width: 768px) {
    flex-direction: column;
  }

  .brand-wrapper {
    display: flex;
    flex-direction: column;
    margin-bottom: 2rem;

    p {
      max-width: 250px;
      color: var(--text-soft);
      font-size: 0.8rem;
    }
  }

  .links {
    display: flex;
    gap: 1rem;
    flex: 1;

    .links-group {
      display: flex;
      flex-direction: column;
      flex: 1;

      h3 {
        margin-bottom: 1rem;
        font-size: 1rem;
      }

      a {
        padding: 0.25rem 0;
      }
    }
  }
}
</style>
