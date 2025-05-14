<template>
  <div class="card">
    <header class="section-header" @click="$emit('toggle')">
    <h2>{{item.question}}</h2>
      <button aria-label="toogle-accordion">
        <img :src="srcUrl" alt="isOpen ? 'close answer' : 'open answer'">
      </button>
    </header>
    <article v-show="isOpen">
      <p>
        {{item.answer}}
      </p>
    </article>
    <div class="divider" v-if="!isLast"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      openBtn: require('@/assets/images/icon-plus.svg'),
      closeBtn: require('@/assets/images/icon-minus.svg')
    }
  },
  props: {
    item: {
      type: Object,
      required: true
    },
    isOpen: {
      type: Boolean,
      default: false
    },
    isLast: { // 新增 prop，表示是否是最后一项
      type: Boolean,
      default: false
    }
  },
  computed: {
    srcUrl () {
      return this.isOpen ? this.openBtn : this.closeBtn
    }
  }
}
</script>

<style lang="less" scoped>
@import '@/styles/card.less';
</style>
