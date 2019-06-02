<template>
  <div class="index">
    <img class="cover" src="../assets/cover.jpg" alt="">
    <div class="abstract">
      <img class="abstract-left" src="" alt="">
      <img class="abstract-right" src="../assets/abstract.jpg" alt="">
    </div>
    <div class="introductions">
      <introduction
        v-for="(item, index) in introductions"
        :key="index"
        :message="item.message"
        :img="item.img"
        :button="item.button"
        :url="item.url"
      />
    </div>
  </div>
</template>

<script>
import IndexIntroduction from './IndexIntroduction'
export default {
  name: 'Index',
  data () {
    return {
      introductions: [
        {
          message: 'hhhh',
          img: require('../assets/hard.jpg'),
          button: 'Read More',
          url: 'https://www.baidu.com'
        },
        {
          message: 'hhhh',
          img: require('../assets/hard.jpg'),
          button: 'Read More',
          url: 'https://www.baidu.com'
        },
        {
          message: 'hhhh',
          img: require('../assets/hard.jpg'),
          button: 'Read More',
          url: 'https://www.baidu.com'
        },
        {
          message: 'hhhh',
          img: require('../assets/hard.jpg'),
          button: 'Read More',
          url: 'https://www.baidu.com'
        }
      ]
    }
  },
  components: {
    'introduction': IndexIntroduction
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cover{
  width: 100%;
}
.abstract{
  display: flex;
  flex-direction: row;
  width: 100%;
}
.abstract-left{
  width: 39%;
}
.abstract-right{
  width: 61%;
}
.introductions{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>
