<template>
  <div class="app">
    <section>
      <header>
        <img src="@/assets/images/icon-star.svg" alt="" aria-hidden="true">
        <h1>FAQs</h1>
      </header>
      <AccordionCard
      v-for="(item, index) in FAQsList"
      :key="index"
      :item="item"
      :is-open="activeIndex === index"
      @toggle="handleToggle(index)"
      :is-last="index === FAQsList.length - 1"
      ></AccordionCard>
    </section>
  </div>
</template>

<script>
// import axios from 'axios'
import AccordionCard from './components/AccordionCard.vue'
import faqsData from '@/assets/data/faqs.json'
export default {
  name: 'App',
  data () {
    return {
      FAQsList: [],
      activeIndex: 0 // 存储当前展开项的索引
    }
  },
  components: {
    AccordionCard
  },
  created () {
    this.getFAQsList()
  },
  methods: {
    // async getFAQsList () {
    //   const res = await axios.get('http://localhost:3000/faqs')
    //   this.FAQsList = res.data
    //   console.log(this.FAQsList)
    // },
    getFAQsList () {
      // 直接从导入的JSON数据获取
      this.FAQsList = faqsData.faqs
      console.log(this.FAQsList)
    },
    handleToggle (index) {
      // 如果点击的是已展开的项，则关闭；否则展开新项
      this.activeIndex = this.activeIndex === index ? null : index
    }
  }
}
</script>

<style lang="less">
@import '@/styles/index.less';
</style>
