<template>
  <div>{{ item }} <slot/></div>
</template>

<script>
export default {
  name: 'ListItem',
  props: {
    item: {
      type: String,
      required: true,
    },
  },
};
</script>
