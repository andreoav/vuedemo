<template>
  <div class="header">
    <form v-on:submit.prevent="submitForm">
      <input type="text" v-model="item">
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'HeaderBar',
  data() {
    return {
      item: '',
    };
  },
  props: {
    onAddItem: {
      type: Function,
      required: true,
    },
  },
  methods: {
    submitForm() {
      if (this.item) {
        this.onAddItem(this.item);
        this.item = '';
      }
    },
  },
};
</script>
