<template>
  <div>
    <h1>Looping through array of objects</h1>
    <ul>
      <li v-for="(item, n) in interests" :key="item.title">
        {{ item.title }}
        <ol v-if="item.favorites && item.favorites.length > 0">
          <li v-for="(fav, n) in item.favorites" :key="fav">
            {{ fav }}
          </li>
        </ol>
      </li>
    </ul>
  </div>
</template>

<script setup>
  const interests = [
    {
      title: 'TV',
      favorites: ["Designated Survivor", "Spongebob"]
    },
    {
      title: "Games",
      favorites: ["CS:GO"]
    },
    {
      title: "Sports",
      favorites: []
    }
  ]
</script>

<style>

</style>