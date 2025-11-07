<script setup>
import SectionHead from '@/components/ui/SectionHead.vue'
import PlusIcon from '@/assets/icons/plus.svg'
import MinusIcon from '@/assets/icons/minus.svg'
import { ref } from 'vue'

const faqSection = {
  title: "GOT QUESTIONS? WE'VE GOT ANSWERS.",
  questionsAndAnswers: [
    {
      id: 1,
      question: 'How do I turn a website into an app?',
      answer:
        'Enter your **URL**, customize the design, then build. You can convert your website to an app **without coding** and test it on real devices using our simple no-code builder.',
    },
    {
      id: 2,
      question: 'Can I convert my website to app for free?',
      answer:
        'Yes! We offer a **Free 30-Day Plan** (for both Android and iOS) that includes all features, allowing you to test, customize, and even build your app to ensure it meets your needs before committing to a paid plan.',
    },
    {
      id: 3,
      question: 'Does the app stay updated when I update my website?',
      answer:
        'Absolutely. Appilix uses **Live Sync** technology. As long as your app is using a standard webview, any content changes you make on your live website will be automatically reflected in the app without needing to rebuild or republish.',
    },
    {
      id: 4,
      question: 'Are there any hidden costs for publishing to the app stores?',
      answer:
        'No **hidden extra charges**. Our pricing is clear and includes unlimited builds. However, please note that Apple and Google charge their own separate annual developer fees (not paid to Appilix) for maintaining your developer accounts.',
    },
    {
      id: 5,
      question: 'How do Push Notifications work?',
      answer:
        'We use **Google Firebase** integration. Once the Firebase module is connected, you can send unlimited, customized push notifications to all your app users directly from the Appilix dashboard to bring them back to your site.',
    },
  ],
}

const currentOpenFAQ = ref(null)

const openFAQusetion = (id) => {
  currentOpenFAQ.value = faqSection.questionsAndAnswers.find((i) => i.id === id)
}

const closeFAQusetion = () => {
  currentOpenFAQ.value = null
}
</script>

<template>
  <section id="faqs" class="section faq-section">
    <SectionHead :title="faqSection.title" />

    <div class="questions-and-awnsers">
      <div class="faq-card" v-for="faq in faqSection.questionsAndAnswers" :key="faq.id">
        <div class="question-wrapper">
          <h2 class="question">{{ faq.question }}</h2>
          <MinusIcon v-if="currentOpenFAQ?.id === faq.id" class="icon" @click="closeFAQusetion" />
          <PlusIcon v-else class="icon" @click="openFAQusetion(faq.id)" />
        </div>
        <p v-if="currentOpenFAQ?.id === faq.id" class="answer">{{ faq.answer }}</p>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.faq-section {
  .questions-and-awnsers {
    max-width: 680px;
    margin: 0 auto;
    margin-top: 2rem;

    .faq-card {
      background: var(--accent-900);
      border: 1px solid var(--accent-800);
      border-radius: 1rem;
      margin-bottom: 1rem;
      padding: 1rem;

      .question-wrapper {
        display: flex;
        justify-content: space-between;

        .question {
          font-weight: 400;
          font-size: 1.1rem;
        }

        .icon {
          cursor: pointer;
        }
      }

      .answer {
        margin-top: 1rem;
      }
    }
  }
}
</style>
