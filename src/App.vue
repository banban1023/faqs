<template>
  <div class="app">
    <section>
      <header>
        <img src="@/assets/images/icon-star.svg" alt="" aria-hidden="true">
        <h1>FAQs</h1>
      </header>
      <main>
        <AccordionCard></AccordionCard>
      </main>
    </section>
  </div>
</template>

<script>
import AccordionCard from './components/AccordionCard.vue'
export default {
  name: 'App',
  components: {
    AccordionCard
  }
}
</script>

<style lang="less">
@import '@/styles/index.less';
</style>
