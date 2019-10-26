<template>
  <div id="app">
      <router-view/>
  <!--   <div class="navbox">
      <div v-for="(item,index) in navroom" :key="index" class="itembox" @click="slet(index)">{{item}}</div>
    </div>
    <iframe :src="pathurl" frameborder="0" class="box"></iframe> -->
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      navroom: [
        "http://www.baidu.com",
        "https://www.taobao.com",
        "https://www.jd.com"
      ],
      pathurl: "http://www.baidu.com"
    };
  },
  mounted() {
    console.log(this.$router.options.routes.path);
  },
  methods:{
    slet(index){
      this.pathurl=this.navroom[index]
    }
  }
};
</script>

<style>
#app {
   width: 100vw;
  height: 100vh;
  overflow: hidden;
  margin: 0;
  padding: 0;
}
.navbox {
  display: flex;
  flex-flow: row;
  justify-content: flex-start;
  align-items: center;
  width: calc(100vw - 1px);
  height:58px;
  border: 1px solid #ccc;
  border-right: none;
}
.itembox {
  width: calc(100vw / 3 - 3px);
  height: 58px;
  border-right: 1px solid #ccc;
}
.box {
  width: 100vw;
  height: calc(100vh - 60px);
}
</style>
