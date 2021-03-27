<template>
  <router-view v-slot="{ Component }">
    <transition :name="transitionName" mode="out-in">
      <keep-alive>
        <component :is="Component"/>
      </keep-alive>
    </transition>
  </router-view>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
  name: 'App',
  data() {
    return {
      transitionName: ''
    }
  },
  watch: {
    $route(to, from) {
      //如果to的索引值为0，不添加任何动画；如果to索引大于from索引,判断为前进状态,反之则为后退状态
      if(to.meta.index > 0){
        if( to.meta.index < from.meta.index){
          this.transitionName = 'slide-right';
        }else{
          this.transitionName = 'slide-left';
        }
      }else if(to.meta.index == 0 && from.meta.index > 0){
        this.transitionName = 'slide-right';
      }

      //当然，如果你没有需要设置索引值为0的页面可以直接用着一段
      /*if( to.meta.index < from.meta.index){
            this.transitionName = 'slide-right';
      }else{
            this.transitionName = 'slide-left';
      }*/
    }
  }
})
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
  overflow: auto;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
