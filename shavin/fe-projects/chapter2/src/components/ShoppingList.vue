<template>
  <div>
    <h1>Shopping List</h1>
    <div :class="$style.itemInput">
      <input type="text" v-model="newItem" placeholder="Enter a new item"/>
      <button @click="addItem()">Add Item</button>
    </div>
    <ul v-if="shoppingItems && shoppingItems.length > 0">
      <li v-for="item in shoppingItems" :key="item">
        {{ item }}
        <button @click="deleteItem(item)">Remove</button>
      </li>
    </ul>
    <button @click="clearList()" :class="$style['clear-all']">Delete All</button>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        newItem: "",
        shoppingItems: [
          "Apples", "Bananas", "Carrots"
        ]
      }
    },
    methods: {
      addItem(){
        if(this.newItem && this.newItem.length > 2){
          this.shoppingItems = [...this.shoppingItems, this.newItem];
          this.newItem = "";
        }
      },
      deleteItem(item){
        this.shoppingItems = this.shoppingItems.filter(i => i !== item);
      },
      clearList(){
        this.shoppingItems = [];
      }
    }
  }
</script>

<style lang="scss" module>
  @import '../styles/typography.scss';

  li {
    display: flex;
    justify-content: space-between;
    padding: 5px;
    > button {
      text-transform: uppercase;
      color: orangered;
      background-color: #eee;
      padding: 5px;
      border-radius: 1rem;
      border: 1px solid orangered;
    }
    > button:hover {
      color: #eee;
      background-color: orangered;
    }
  }
  .itemInput {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0 auto;
    max-width: 400px;
    padding: 5px;
    border: 1px solid rgba(0,0,0,0.25);
    > input {
      width: 75%;
      padding: 5px;
    }
    > button {
      background-color: $color-blue;
      padding: 5px;
      color: #eee;
      border-radius: 1rem;
      border: 1px solid $color-blue;
    }
    > button:hover {
      background-color: #eee;
      color: $color-blue;
    }
  }

  .clear-all {
    display: block;
    margin: 0 auto;
    width: 100%;
    max-width: 410px;
    padding: 15px;
    margin-top: 5px;
    background-color: orangered;
    color: #eee;
    border: 1px solid orangered;
    border-radius: 1rem;
    text-transform: uppercase;
  }
  .clear-all:hover {
    background-color: #eee;
    color: orangered;
    border: 1px solid orangered;
  }
</style>