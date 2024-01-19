<template>
  <div>
    <h1>{{ upper ? title.toUpperCase() : title }}</h1>
  </div>
</template>

<script setup>
  const title = "My first and a half component";
  const upper = true;
</script>

<style>

</style>