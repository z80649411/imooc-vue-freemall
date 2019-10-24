<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App"
                v-if="isShow"
    />
    <p>{{name}}</p>
    <button @click="update">更新数据</button>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  },

  // 局部
  data() {
    return {
      name: 'Welcome to Vue',
      isShow: true
    }
  },

  methods: {
    update() {
      this.name = 'itPoet';
      this.isShow = !this.isShow;
    }
  },

  // 全局写法
  // data: {
  //
  // },

  beforeCreate() {
    window.console.log('1、beforeCreate');
    window.console.log('$el', this.$el);
    window.console.log('$data', this.$data);
  },

  created() {
    window.console.log('2、created');
    window.console.log('$el', this.$el);
    window.console.log('$data', this.$data);

  },

  beforeMount() {
    window.console.log('3、beforeMount');
    window.console.log('$el', this.$el);
    window.console.log('$data', this.$data);
  },

  mounted() {
    window.console.log('4、mounted');
    window.console.log('$el', this.$el);
    window.console.log('$data', this.$data);
  },

  beforeUpdate() {
    window.console.log('5、beforeUpdate');
    window.console.log('$el', this.$el);
    window.console.log('$data', this.$data);
  },

  updated() {
    window.console.log('6、updated');
  },

  beforeDestroy() {
    window.console.log('7、beforeDestroy');
  },

  destroyed() {
    window.console.log('8、destroyed');
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
