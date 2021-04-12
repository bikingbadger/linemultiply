<template>
  <div :class="classObject"></div>
  <div
    v-for="i in numLines"
    :key="i"
    class="line-vertical"
    :class="classObject"
  ></div>
</template>

<script>
export default {
  props: { numLines: Number, lineType: String },
  computed: {
    classObject() {
      return {
        'line-horizontal': this.lineType === 'horizontal',
      };
    },
  },
};
</script>

