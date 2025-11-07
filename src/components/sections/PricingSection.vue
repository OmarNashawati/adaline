<script setup>
import { computed, ref } from 'vue'
import SectionHead from '../ui/SectionHead.vue'
import Button from '../ui/Button.vue'

const prices = {
  androidPlans: [
    {
      planName: 'Free',
      price: '$0.00',
      billingCycle: "Let's build your first Android app for free and explore for 30 days.",
      features: [
        '1 Android Application',
        'Play Store Releasable',
        'No Appilix Logo',
        'AdMob Ads',
        'Push Notifications',
        'All Integration Modules',
      ],
    },
    {
      planName: 'Lifetime',
      price: '$89.00',
      billingCycle: 'Get all premium features forever with no renewal worries.',
      features: [
        '1 Android Application',
        'Unlimited Builds',
        'Unlimited Active Users',
        'Play Store Releasable',
        'No Appilix Logo',
        'AdMob Ads',
        'Push Notifications',
        'All Integration Modules',
      ],
    },
    {
      planName: 'Yearly',
      price: '$69.00',
      billingCycle: 'Billed annually with all features and updates included.',
      features: [
        '1 Android Application',
        'Unlimited Builds',
        'Unlimited Active Users',
        'Play Store Releasable',
        'No Appilix Logo',
        'AdMob Ads',
        'Push Notifications',
        'All Integration Modules',
      ],
    },
  ],
  iosPlans: [
    {
      planName: 'Free',
      price: '$0.00',
      billingCycle: 'Test out the app builder for 30 days.',
      features: [
        '1 iOS Application',
        'Apple Store Releasable',
        'No Appilix Logo',
        'AdMob Ads',
        'Push Notifications',
        'All Integration Modules',
      ],
    },
    {
      planName: 'Lifetime',
      price: '$139.00',
      billingCycle: 'Get all premium features forever with no renewal worries.',
      features: [
        '1 iOS Application',
        'Unlimited Builds',
        'Unlimited Active Users',
        'Apple Store Releasable',
        'No Appilix Logo',
        'AdMob Ads',
        'Push Notifications',
        'All Integration Modules',
      ],
    },
    {
      planName: 'Yearly',
      price: '$79.00',
      billingCycle: 'Billed annually with all features and updates included.',
      features: [
        '1 iOS Application',
        'Unlimited Builds',
        'Unlimited Active Users',
        'Apple Store Releasable',
        'No Appilix Logo',
        'AdMob Ads',
        'Push Notifications',
        'All Integration Modules',
      ],
    },
  ],
}

const selectedPlatform = ref('android')

const pricesList = computed(() =>
  selectedPlatform.value === 'android' ? prices.androidPlans : prices.iosPlans,
)
</script>

<template>
  <section id="pricing" class="section pricing-section">
    <SectionHead
      title="Transparent Pricing, No Surprises"
      discription="Simple, Flexible Plans to Turn Your Website into a Mobile App No-coding Required."
    />

    <div class="packages-wrapper">
      <div class="platform-selection">
        <label for="android" :class="{ selected: selectedPlatform === 'android' }">
          Android Plans
          <input id="android" type="radio" value="android" v-model="selectedPlatform" />
        </label>

        <label for="iso" :class="{ selected: selectedPlatform === 'iso' }">
          ISO Plans
          <input id="iso" type="radio" value="iso" v-model="selectedPlatform" />
        </label>
      </div>

      <div class="price-cards">
        <div class="price-card" v-for="price in pricesList">
          <p class="title">{{ price.planName }}</p>
          <p class="price">{{ price.price }}</p>
          <p class="description">{{ price.billingCycle }}</p>
          <Button type="secondary" class="start-button">Get Started</Button>
          <ul class="features">
            <li v-for="feature in price.features">{{ feature }}</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.pricing-section {
  .packages-wrapper {
    margin-top: 2rem;

    .platform-selection {
      border: 1px solid var(--accent-700);
      border-radius: 0.25rem;
      overflow: hidden;
      background: var(--accent-900);
      width: fit-content;
      margin: 0 auto;
      height: 40px;
      display: flex;
      font-size: 0.8rem;

      label {
        height: 100%;
        padding: 0 8px;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        border-radius: 0.25rem;
        transition: all 0.5s ease;

        &.selected {
          background: var(--accent-300);
        }

        input[type='radio'] {
          display: none;
        }
      }
    }

    .price-cards {
      display: grid;
      grid-template-columns: repeat(3, 280px);
      gap: 1rem;
      justify-content: center;
      margin-top: 2rem;

      @media (max-width: 768px) {
        grid-template-columns: repeat(1, 100%);
      }

      .price-card {
        display: flex;
        flex-direction: column;
        gap: 1rem;
        padding: 1.5rem;
        background: var(--accent-900);
        border-radius: 1rem;
        border: 1px solid var(--accent-800);

        .title {
          font-weight: 600;
          margin-bottom: 1rem;
        }

        .price {
          font-size: 1.7rem;
          font-weight: 100;
        }
        .start-button {
          width: 100%;
        }

        .features {
          display: block;
          list-style-type: disc;
          margin-block-start: 0;
          margin-block-end: 0;
          padding-inline-start: 20px;
          unicode-bidi: isolate;

          li {
            padding: 0.25rem 0;
          }
        }
      }
    }
  }
}
</style>
