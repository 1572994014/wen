<template>
  <div id="app">
    <div class="header">
      <header>
        <div class="header-warpper">
          <h1 class="logo">WEN UI</h1>
          <div class="nav">仿饿了么</div>
        </div>
      </header>
    </div>
    <div class="main">
      <div class="main-warpper">
        <div class="main-nav">
          <ul>
            <li>
              <a @click="jump">组件1</a>
            </li>
          </ul>
        </div>
        <div class="main-content">
          <router-view/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  methods: {
    jump () {
      console.log(123)
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
  body, html, h1, ul, li, a {
    margin: 0;
    padding: 0;
    font-family: Helvetica Neue,Helvetica,PingFang SC,Hiragino Sans GB,Microsoft YaHei,SimSun,sans-serif;
    font-weight: 400;
  }
  li {
    list-style: none;
  }
  a {
    color: #409eff;
    text-decoration: none;
  }
  .header{
    height: 80px;
  }
  .header header{
    height: 80px;
  }
  .header-warpper{
    width: 1140px;
    height: 100%;
    margin: 0 auto;
    box-sizing: border-box;
    border-bottom: 1px solid #dcdfe6;
  }
  .logo{
    float: left;
    height: 80px;
    line-height: 80px;
  }
  .nav{
    float: right;
    line-height: 80px;
  }
  .main-warpper{
    width: 1140px;
    margin: 0 auto;
  }
  .main-nav{
    width: 240px;
    padding-top: 50px;
    float: left;
  }
  .main-content{
    padding-top: 50px;
    float: left;
  }
  .radio-group .radio-button:nth-child(n+2) span{
    border-left: 0px;
  }
  .radio-group .radio-button:last-child span{
    border-top-right-radius:  4px;
    border-bottom-right-radius:  4px;
  }
  .radio-group .radio-button:first-child span{
    border-top-left-radius:  4px;
    border-bottom-left-radius:  4px;
  }
</style>
