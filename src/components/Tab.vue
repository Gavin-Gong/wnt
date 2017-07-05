<template>
<ul class="wnt-tab clearfix">
  <li
    v-for="(item, index) in data"
    v-if="item.title"
    class="wnt-tab-item">
      <span :class="[index === 1 ? 'is-active' : '']">{{item.title ? item.title : ''}}</span>
     </li>
     <li
      class="wnt-tab-item"
      :class="[$slots.default ? 'item-float' : '']">
      <slot></slot>
     </li>
</ul>
</template>

<script>
export default {
  props: {
    data: {
      type: Array,
      default: []
    }
  }
}
</script>

<style lang="scss">
@import '../styles/mixins';
@import '../styles/vars';
.wnt-tab {
  @include reset-list;
  padding: .5rem;
  padding-left: 1rem;
  background: $baseColor;
  .wnt-tab-item {
    display: inline-block;
    padding: 1rem;
    color: $normalFont;
    span {
      padding-bottom: .4rem;
    }
    &:fist-child {
      padding-left: .5rem;
    }
  }
  .is-active {
    border-bottom: 2px solid #fff;
  }
  .item-float {
    float: right;
  }
}
</style>
