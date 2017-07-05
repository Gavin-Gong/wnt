<template>
  <li class="wnt-listitem">
    <div class="left-wrapper">
      <p class="item-desc">{{data.desc}}</p>
      <div class="tag-bar clearfix">
        <slot></slot>
      </div>
    </div>
    <div class="right-wrapper">
      <!--<img :src="data.imgurl" alt="">-->
      <div class="image-box" :style="{backgroundImage: `url(${data.imgurl})`}"></div>
    </div>
  </li>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      required: true
    }
  }
}
</script>

<style lang="scss">
@import '../styles/mixins';
.wnt-listitem {
  display: flex;
  justify-content: space-between;
  margin-bottom: 1rem;
  &:last-child {
    margin-bottom: 0;
    border-bottom: 1px solid #bbb;
  }
  .left-wrapper {
    width: 50%;
    padding: 1rem;
    padding-left: 0rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    .item-desc {
      font-size: 12px;
    }
    .tag-bar {
      float: right;
    }
  }
  .right-wrapper {
    width: 50%;
    .image-box {
      background: center center no-repeat;
      background-size: cover;
      height: 10rem;
    }
  }
}
</style>
