<template>
  <div>
    <h1 v-once v-text="text"></h1>
    <a
      :href="link.url"
      :target="link.target"
      :tabindex="link.tabindex"
    >{{ link.title }}</a>
  </div>
</template>

<script setup>
  const text = "Directive text";
  const link = {
    title: "Go to Bing",
    url: "https://bing.com",
    tabindex: 1,
    target: "_blank"
  }
</script>

<style>

</style>