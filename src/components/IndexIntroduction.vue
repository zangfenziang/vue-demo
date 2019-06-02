<template>
  <div class="index-introduction">
    <img :src="img" alt="">
    <div class="index-introduction-block">
      <span>{{ message }}</span>
      <el-button @click="onClick">{{ button }}</el-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexIntroduction',
  props: ['message', 'img', 'button', 'url'],
  methods: {
    onClick: function () {
      window.location.href = this.url
    }
  }
}
</script>

<style scoped>
.index-introduction{
  width: 300px;
  position: relative;
}
.index-introduction>img{
  width: 100%;
}
.index-introduction>div{
  position: absolute;
  bottom: 0;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.index-introduction>div>span{
  margin-bottom: 10px;
}
</style>
