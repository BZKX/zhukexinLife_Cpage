<template>
  <div class="home">
    <h1>Home Page</h1>
    <a-space>
      <a-button @click="goPage('/about')" type="primary">About</a-button>
      <a-button @click="goPage('/formBuilder')" type="primary">formBuilder</a-button>
    </a-space>
  </div>
</template>

<script lang="ts">
import {defineComponent} from 'vue';
import {RouteLocationRaw} from 'vue-router';

export default defineComponent({
  name: 'Home',
  components: {},
  methods: {
    goPage(path: RouteLocationRaw) {
      this.$router.push(path)
    }
  }
});
</script>
