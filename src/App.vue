<template>
  <div class="App">
    <div>
      // router-link 组件 用来导航到哪个路由
      <router-link to="/Home">go Home</router-link>
      <router-link to="/About">go About</router-link>
    </div>
    <div>
      <p>{{getCounter}}</p>
      <button @click="add">add</button>
    </div>
    <div>
      // 用于展示匹配到的路由视图组件
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'
export default {
  name: 'App',
  data() {
    return {};
  },
  computed: {
    ...mapGetters(['getCounter'])
  },
  methods: {
    ...mapActions(['add'])
  }
};
</script>

<style lang="scss" scoped>
.App {
  text-align: center;
  color: skyblue;
  font-size: 28px;
}
</style>