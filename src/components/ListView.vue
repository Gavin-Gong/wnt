<template>
<ul class="wnt-listview">
  <li class="wnt-listview-head clearfix">
    <p>{{title}}</p>
    <i class="iconfont icon-menu more-btn"></i>
  </li>
  <slot></slot>
</ul>
</template>

<script>
export default {
  props: {
    title: {
      type: String
    }
  }
}
</script>

<style lang="scss">
@import '../styles/mixins';
@import '../styles/vars';
.wnt-listview {
  @include reset-list;
  // padding: 0 .6rem;
  .wnt-listview-head {
    margin-bottom: 1rem;
    p {
      display: inline-block;
      color: $secondFont;
      font-size: 14px;
    }
    .more-btn {
      float: right;
      color: $secondFont
    }
  }
}
</style>
