<template>
  <div class="about">
    <h1>About Page</h1>
    <a-space>
      <a-button @click="goPage('/')" type="primary">Home</a-button>
      <a-button @click="goPage('/formBuilder')" type="primary">formBuilder</a-button>
    </a-space>
  </div>
</template>
<script lang="ts">
import {defineComponent} from 'vue';
import {RouteLocationRaw} from 'vue-router';

export default defineComponent({
  name: 'About',
  components: {},
  methods: {
    goPage(path: RouteLocationRaw) {
      this.$router.push(path)
    }
  }
})
</script>
