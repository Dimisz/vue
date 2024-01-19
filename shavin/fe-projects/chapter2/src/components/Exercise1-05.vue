<template>
  <h1>Looping through arryas</h1>
  <ul v-for="(item, index) in interests">
    <li :key="index">{{ item }}</li>
  </ul>
</template>

<script setup>
  const interests = ["TV", "Games", "Sports"];
</script>

<style>

</style>