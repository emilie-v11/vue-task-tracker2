<script>
export default {
  name: 'Button',
  props: {
    color: {
      type: String,
    },
    text: {
      type: String,
    },
  },
  methods: {
    onClick() {
      this.$emit('btn-click');
    },
  },
};
</script>

<template>
  <button @click="onClick()" :style="{ background: color }" class="btn">{{ text }}</button>
</template>
