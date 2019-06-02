<template>
  <div id="app">
    <div id="header">
      <div id="guide">
        <div id="logo">
          <img id="zju-logo" src="./assets/logo.jpg" alt="">
        </div>
        <div id="link">
          <el-dropdown>
            <span class="el-dropdown-link">
                A<i class="el-icon-arrow-down el-icon--right"></i>
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item @click.native="routTo('team')">aaa</el-dropdown-item>
              <el-dropdown-item>bbb</el-dropdown-item>
              <el-dropdown-item>ccc</el-dropdown-item>
              <el-dropdown-item>ddd</el-dropdown-item>
              <el-dropdown-item divided>eee</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <el-dropdown>
            <span class="el-dropdown-link">
              B<i class="el-icon-arrow-down el-icon--right"></i>
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>aaa</el-dropdown-item>
              <el-dropdown-item>bbb</el-dropdown-item>
              <el-dropdown-item>ccc</el-dropdown-item>
              <el-dropdown-item>ddd</el-dropdown-item>
              <el-dropdown-item divided>eee</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <el-dropdown>
            <span class="el-dropdown-link">
              C<i class="el-icon-arrow-down el-icon--right"></i>
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>aaa</el-dropdown-item>
              <el-dropdown-item>bbb</el-dropdown-item>
              <el-dropdown-item>ccc</el-dropdown-item>
              <el-dropdown-item disabled>ddd</el-dropdown-item>
              <el-dropdown-item divided>eee</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <span class="el-dropdown-link">
            D
          </span>
        </div>
      </div>
      <el-progress :percentage="percent" :show-text=false :stroke-width=6 />
    </div>
    <div id="header-block"></div>
    <router-view/>
    <div id="tail" style="margin-top: 10px; background-color: #181818;">
      <div id="tail-word">
        <div id="tail-logo">
          <div class="zju-igem">ZJU-iGEM</div>
          <div style="color: #fff; height: 30px; line-height: 30px; padding: 10px;">
            <i class="el-icon-phone" style="color: gray;"></i>
            400-706-6615
          </div>
          <div id="out-link-logo" style="padding: 10px;">
            <img src="./assets/weixin.svg" alt="">
            <img src="./assets/weibo.svg" alt="">
            <img src="./assets/in.svg" alt="">
          </div>
        </div>
        <div class="word-about">
          <div class="word-about-header">其他</div>
          <div>华大基因</div>
          <div>华大医学</div>
          <div>体外诊断</div>
          <div>合成生物学</div>
        </div>
        <div class="word-about">
          <div class="word-about-header">热门产品</div>
          <div>人全基因组重测序</div>
          <div>宏基因组测序</div>
          <div>ATAC-Seq</div>
          <div>10X Genomics 单细胞 RNA-SEq</div>
        </div>
        <div class="word-about">
          <div class="word-about-header">市场活动</div>
          <div>产品促销</div>
          <div>会议</div>
          <div>网络课程</div>
        </div>
        <div class="word-about">
          <div class="word-about-header">资源下载</div>
          <div>发表文章</div>
          <div>研究方案</div>
          <div>分析软件</div>
          <div>知识库</div>
        </div>
        <div class="word-about">
          <div class="word-about-header">关于我们</div>
          <div>公司简介</div>
          <div>质量体系</div>
          <div>服务指南</div>
          <div>加入我们</div>
          <div>联系我们</div>
        </div>
      </div>
      <div style="height: 1px; width: 100%; background-color: gray; margin: 5px 0;"></div>
      <div style="color: gray; text-align: center; width: 100%; font-size: 12px; margin-top: 15px;">
        Copyright&copy;深圳华大基因科技服务有限公司保留所有权利。 粤icp备 12059600
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      percent: 0
    }
  },
  created: function () {
    let ts = this
    window.addEventListener('scroll', function () {
      const top = document.documentElement.scrollTop || document.body.scrollTop
      const height = document.body.scrollHeight - document.body.offsetHeight
      ts.percent = top / height * 100
    })
  },
  methods: {
    routTo: function (str) {
      this.$router.push(str)
    }
  }
}
</script>

<style>
html, body{
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100%;
}
#header{
  width: 100%;
  height: 120px;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 10;
  background-color: #fff;
}
#guide{
  max-width: 1280px;
  margin: 0 auto;
  height: calc(100% - 6px);
}
#logo{
  width: calc(30% - 20px);
  height: calc(100% - 20px);
  float: left;
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin: 10px;
}
#link{
  width: 70%;
  height: 100%;
  float: right;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
#zju-logo{
  max-width: 100%;
  max-height: 100%;
}
#header-block{
  height: 120px;
}
#tail{
  width: calc(100% - 60px);
  padding: 30px;
  padding-bottom: 20px;
}
#tail-word{
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  align-items: flex-start;
  justify-content: space-between;
}
#tail-logo{
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
}
#out-link-logo img{
  width: 30px;
  color: gray;
}
.el-dropdown{
  margin: 0 20px;
}
.el-dropdown-link {
  cursor: pointer;
  color: #000;
  font-size: 24px;
}
.el-dropdown-menu__item{
  font-size: 24px;
}
.zju-igem{
  background-color: #000;
  width: 180px;
  height: 60px;
  line-height: 60px;
  text-align: center;
  color: #fff;
  font-weight: bold;
  font-size: 30px;
}
.word-about{
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-items: flex-start;
  color: gray;
  line-height: 30px;
}
.word-about .word-about-header{
  line-height: 20px;
  font-size: 20px;
  font-weight: bold;
  color: #fff;
  margin-bottom: 20px;
}
</style>
