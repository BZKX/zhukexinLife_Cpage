<template>
  <div class="main">
    <h1>formBuilder Page</h1>
    <a-space>
      <a-button @click="goPage('/')" type="primary">Home</a-button>
      <a-button @click="goPage('/about')" type="primary">About</a-button>
    </a-space>
  </div>
</template>

<script lang="ts">
import {defineComponent} from 'vue'
import {RouteLocationRaw} from 'vue-router'

export default defineComponent({
  name: "formBuilder",
  methods: {
    goPage(path: RouteLocationRaw) {
      this.$router.push(path)
    }
  }
})
</script>

<style scoped>

</style>
