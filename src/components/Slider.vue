<template>
<ul class="wnt-slider">
  <li
    class="wnt-slider-item"
    v-for="(item, index) in data"
    :class="[focusIndex === index ? 'is-active' : '']">
    <div
      class="image-box"
      :style="{backgroundImage: `url(${item.imgurl})`}">
    </div>
    <!--<img :src="item.imgurl"></img>-->
    <h1>{{ item.title }}</h1>
    <p>{{ item.desc }}</p>

  </li>
  <ul class="nwt-slider-nav">
    <li
      class="nwt-slider-nav-dot"
      :class="[focusIndex === index ? 'is-active' : '']"
      v-for="(item, index) in data.length"></li>
  </ul>
</ul>
</template>

<script>
export default {
  props: {
    data: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      focusIndex: 0,
      timerId: null,
      interval: 800
    }
  },
  methods: {
    startCircle () {
      this.timerId = setInterval(() => {
        if (this.focusIndex + 1 === this.data.length) {
          this.focusIndex = 0
        } else {
          this.focusIndex = this.focusIndex + 1
        }
      }, 2000)
    }
  },
  mounted () {
    this.startCircle()
  },
  beforeDestroy () {
    clearInterval(this.timerId)
  },
  deactivated () {
    clearInterval(this.timerId)
  }
}
</script>

<style lang="scss">
@import '../styles/mixins';
@import '../styles/vars';
.wnt-slider {
  @include reset-list;
  .wnt-slider-item {
    text-align: center;
    display: none;
    &.is-active {
      display: block;
    }
    .image-box {
      width: 100%;
      min-height: 16rem;
      height: 100%;
      background: center center no-repeat;
      background-size: cover;
    }
    h1 {
      margin: .8rem 0 1rem;
      font-weight: normal;
      font-size: 24px;
    }
    p {
      margin: 0;
      font-size: 12px;
    }
  }
  .nwt-slider-nav {
    @include reset-list;
    // display: inline-block;
    text-align: center;
    margin:  2rem auto;
    >li {
      display: inline-block;
      margin-left: 1rem;
      width: .8rem;
      height:  .8rem;
      border-radius: 50%;
      background: gray;
      &.is-active {
        background: $baseColor;
      }
      &:first-child {
        margin-left: 0;
      }
    }
  }
}
</style>
