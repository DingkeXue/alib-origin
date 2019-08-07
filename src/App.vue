<template>
  <div id="app">
    <!--导航栏-->
    <app-navbar></app-navbar>
    <!--主体部分-->
    <app-content id="content"></app-content>
    <!--底部-->
    <app-footer></app-footer>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
import Content from './components/Content.vue'

export default {
  name: 'app',
  components: {
    'app-navbar': NavBar,
    'app-footer': Footer,
    'app-content': Content
  }
}
</script>

<style>
/*=======初始化标签样式=======*/
@font-face {
  font-family: 'PingFang-Thin';
  src: url('./font/PingFang-SC-Thin.otf');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'Rufina-Regular';
  src: url('./font/Rufina-Regular.ttf');
  font-weight: normal;
  font-style: normal;
}


body,p,h1,h2,h3,h4,h5,h6,hr,p,ol,li,ul,form,button,input,textarea {
  margin: 0;
  padding: 0;
}

body,button,input,select {
  font: 12px/1.5 '\5FAE\8F6F\96C5\9ED1','\5b8b\4f53',tahoma,arial;
}

a {
  text-decoration: none;
}

#app {
  color: white;
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.container {
  width: 1000px;
  margin: 0 auto;
  overflow: hidden;
}

#content {
  flex: 1;
}

@media screen and (min-width: 1440px){
  #index-image {
    width: 100%;
  }
}
</style>
