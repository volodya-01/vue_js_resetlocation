<template>
  <div class="hello">
    <div class="outbox">
      <div class="inbox" :style="isstyle">
        <h1>{{ msg }}</h1>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      isstyle: ''
    };
  },
  mounted() {
    var _this = this;
    _this.getnumfun();
    setInterval(() => {
      _this.getnumfun();
    }, 1000);
  },
  methods: {
    getnumfun() {
      var x=parseInt(Math.random()*100)
      var y=parseInt(Math.random()*100)
      this.resetlocation(x, y);
    },
    resetlocation(x, y) {
      this.isstyle = `top:${y}px;left:${x}px`;
      console.log("123")
      console.log("456")
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
}
.outbox {
  width: 50vw;
  height: 50vh;
  border: 2px #444 solid;
  position: relative;
}
.inbox {
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
  width: 200px;
  height: 200px;
  background-color: red;
  position: absolute;
}
h1 {
  font-weight: normal;
}
</style>
