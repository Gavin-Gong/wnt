<template>
  <div id="app">
    <tab :data="tabData" class="tab">
      <i class="iconfont icon-uicon_camera tab-camera"></i>
    </tab>
    <slider :data="sliderData"></slider>
    <list-view :title="listViewData">
      <list-item v-for="item in listItemData" :data="item">
        <tag>旅游</tag>
      </list-item>
    </list-view>
  </div>
</template>

<script>
import ListView from './components/ListView'
import ListItem from './components/ListItem'
import Tab from './components/Tab'
import Slider from './components/Slider'
import Tag from './components/Tag'

export default {
  name: 'app',
  components: {
    ListView,
    ListItem,
    Tab,
    Slider,
    Tag
  },
  data () {
    return {
      tabData: [
        { title: '关注', link: '/' },
        { title: '精选', link: '/' },
        { title: '动态', link: '/' }
      ],
      sliderData: [
        { imgurl: 'http://pic.58pic.com/58pic/15/15/32/43x58PICgE2_1024.jpg', title: '上天入地', desc: '旅行让你一次性大饱眼福' },
        { imgurl: 'http://img3.imgtn.bdimg.com/it/u=1613703227,3591205910&fm=200&gp=0.jpg', title: '上天入地!!', desc: '旅行让你一次性大饱眼福' },
        { imgurl: 'http://img5.imgtn.bdimg.com/it/u=2308228914,75701045&fm=26&gp=0.jpg', title: '上天入地!!!!', desc: '旅行让你一次性大饱眼福' }
      ],
      listViewData: '最热标签',
      listItemData: [
        { imgurl: 'http://img0.imgtn.bdimg.com/it/u=1689583646,2560929748&fm=26&gp=0.jpg', desc: '有些事情，如果不是你自己亲身经历过，是不能随便拿来吹的。 而作为一个' },
        { imgurl: 'http://img0.imgtn.bdimg.com/it/u=1689583646,2560929748&fm=26&gp=0.jpg', desc: '有些事情，如果不是你自己亲身经历过，是不能随便拿来吹的。 而作为一' }
      ]
    }
  }
}
</script>

<style lang="scss">
html, body {
  font-size: 62.5%;
}
body {
  margin: 0;
  font-size: 1.6rem
}
p {
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 1rem;
  .tab-camera {
    color: #fff;
    font-size: 24px;
  }
  .tab {
    margin-bottom: .6rem;
  }
}
</style>
