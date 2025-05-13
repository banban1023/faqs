<template>
  <div class="card">
    <div class="section-header" @click="toggleBtn">
    <h2>What is Frontend Mentor, and how will it help me?</h2>
      <button aria-label="toogle-accordion">
        <img :src="srcUrl" alt="">
      </button>
    </div>
    <article>
      Frontend Mentor offers realistic coding challenges to help developers improve their
      frontend coding skills with projects in HTML, CSS, and JavaScript. It's suitable for
      all levels and ideal for portfolio building.
    </article>
  </div>
</template>

<script>
export default {
  data () {
    return {
      openBtn: require('@/assets/images/icon-plus.svg'),
      closeBtn: require('@/assets/images/icon-minus.svg'),
      isOpen: true
    }
  },
  computed: {
    srcUrl () {
      return this.isOpen ? this.openBtn : this.closeBtn
    }
  },
  methods: {
    toggleBtn () {
      this.isOpen = !this.isOpen
    }
  }
}
</script>

<style lang="less" scoped>
@import '@/styles/card.less';
</style>
