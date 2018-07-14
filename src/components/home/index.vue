<style scoped lang="less">
  /*lang="less" rel="stylesheet/less" type="text/css"*/
  .layout{
    border: 1px solid #d7dde4;
    position: relative;
    border-radius: 4px;
    overflow: hidden;
    height: 100vh;
    background: #495060;

  }

  .layout-nav{
    width: 216px;
  }
  .layout-footer-center{
    text-align: center;
  }
  .ivu-layout-content{
    background: black;
    margin-top: 130px;
  }

  .home-title{
    height: 10rem;
    line-height: 5rem;
    color: #fff;
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
    font-size: 3rem;
  }
  .bg-video{
    background: #f5f7f9;
    width: 100%;
    opacity: 0.3;
    position: absolute;
    width: 100%;
    left:0;
    top:-20vh;
    padding: 0px;
  }
.content{
  background: #06101a;
  position: absolute;
  width: 100vw;
  height: 100vh;
  opacity: 0.4;
}
  .door-icon{
    display: inline-block;
    vertical-align: middle;
    height: 32px;
    width: 33px;
    background: url("../../assets/home/door.png");
    background-color: red;
  }
</style>
<template>
  <div class="layout">
    <video class="bg-video" autoplay loop poster="home.jpg" id="bgvid">
      <source src="../../assets/home.mp4" type="video/mp4">
    </video>
    <Layout>
      <div  class="content">
        <div class="home-title" @click="comin">
          <h1>吴思敏个人博客</h1>
          <span class="door-icon"></span>
        </div>
        </div>
  </Layout>
  </div>
</template>
<script>
  export default {
    data () {
      return {

      };
    },
    methods: {
      comin () {
        this.$router.push({ path: "/blog"})
    }
  }
}
</script>
