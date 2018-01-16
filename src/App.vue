<template>
  <div id="app">
    <HeaderBar :onAddItem="addItem"/>
    <ListContainer :onRemoveItem="removeItem" :items="items"/>
  </div>
</template>

<script>
import HeaderBar from './components/Header/HeaderBar';
import ListContainer from './components/List/ListContainer';

export default {
  name: 'App',
  data() {
    return {
      items: [],
    };
  },
  methods: {
    addItem(item) {
      this.items.push(item);
    },
    removeItem(index) {
      this.items.splice(index, 1);
    },
  },
  components: {
    HeaderBar,
    ListContainer,
  },
};
</script>

<style>
</style>
