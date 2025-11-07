<script setup>
import { ref } from 'vue'
import ArrowLeftIcon from '@/assets/icons/arrow-left.svg'
import ArrowRightIcon from '@/assets/icons/arrow-right.svg'
import SectionHead from '../ui/SectionHead.vue'

const reviews = [
  {
    id: 1,
    reviewText:
      '"I converted my Shopify store into an app in under 10 minutes. Appilix made it simple, and our sales went up immediately."',
    userName: 'Maria, E-commerce Owner',
  },
  {
    id: 2,
    reviewText:
      '"The no-code builder was a lifesaver. We launched our mobile app with live syncing in less than a day, avoiding months of developer costs."',
    userName: 'David L., Small Business Founder',
  },
  {
    id: 3,
    reviewText:
      '"The push notifications feature is a game-changer for engagement. Our mobile traffic retention has improved by over 40% since launching the app."',
    userName: 'Sarah K., Marketing Director',
  },
]

const currentReview = ref(reviews[0])

const nextReview = () => {
  const currentReviewIndex = reviews.findIndex((r) => r.id === currentReview.value.id)
  const nextReviewIndex = currentReviewIndex === reviews.length - 1 ? 0 : currentReviewIndex + 1
  currentReview.value = reviews[nextReviewIndex]
}

const previosReview = () => {
  const currentReviewIndex = reviews.findIndex((r) => r.id === currentReview.value.id)
  const previosReviewIndex = currentReviewIndex === 0 ? reviews.length - 1 : currentReviewIndex - 1
  currentReview.value = reviews[previosReviewIndex]
}
</script>

<template>
  <section class="section testimonial-wrap">
    <SectionHead title="Trusted By 120K+ Users Worldwide" />

    <div class="testimonial-carousel">
      <button @click="nextReview"><ArrowLeftIcon /></button>

      <div class="current-review">
        <p class="review">{{ currentReview.reviewText }}</p>
        <p class="writter">{{ currentReview.userName }}</p>
      </div>

      <button @click="previosReview"><ArrowRightIcon /></button>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.testimonial-wrap {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  align-items: center;

  .testimonial-carousel {
    display: flex;
    gap: 2rem;

    .current-review {
      max-width: 600px;
      text-align: center;

      .review {
        font-weight: 600;
      }

      .writter {
        color: var(--text-soft);
        padding: 5px 0;
      }
    }

    button {
      background: var(--accent-900);
      border: 1px solid var(--accent-800);
      color: var(--text);
      border-radius: 100%;
      padding: 5px;
      width: 40px;
      height: 40px;
      cursor: pointer;

      &:hover {
        background: var(--accent-800);
      }
    }
  }
}
</style>
