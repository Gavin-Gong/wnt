<template>
<div class="wnt-tag">
  <slot></slot>
</div>
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
.wnt-tag {
  font-size: 12px;
  color: #fff;
  padding: 0 1.6rem;
  border-radius:2rem;
  float: right;
  background: $baseColor;
}
</style>
