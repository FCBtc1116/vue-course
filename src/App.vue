<script setup>
</script>

<template>
  <div class="App">
    <main>
      <router-view :key="$route.fullPath"></router-view>
    </main>
  </div>
</template>

<style scoped>

</style>
