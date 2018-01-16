<template>
  <div>
    <ul>
      <ListItem v-for="(item, index) in items" :key="index" :item="item" :class="getClass(item)">
        <span @click="onRemoveItem(index)">X</span>
      </ListItem>
    </ul>
    <p v-show="numberOfItems > 0">Total: {{ numberOfItems }}</p>
  </div>
</template>

<script>
import ListItem from './ListItem';

export default {
  name: 'ListContainer',
  props: {
    items: {
      type: Array,
      required: true,
    },
    onRemoveItem: {
      type: Function,
      required: true,
    },
  },
  computed: {
    numberOfItems() {
      return this.items.length;
    },
  },
  methods: {
    getClass(item) {
      return item.length % 2 === 0 ? 'green' : 'red';
    },
  },
  components: {
    ListItem,
  },
};
</script>

<style scoped>
.green {
  color: green;
}
.red {
  color: red;
}
</style>

