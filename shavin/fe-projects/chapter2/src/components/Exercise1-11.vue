<template>
  <div>
    <h1>{{ title }}</h1>
    <h2>{{ subtitle }}</h2>
    <ul>
      <li v-for="item in items" :key="item">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        title: "My list component!",
        subtitle: "Vue JS basics",
        items: ["Item 1", "Item 2", "Item 3"]
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '../styles/typography.scss';

  h1 {
    font-size: 50px;
    color: $color-blue;
  }
</style>