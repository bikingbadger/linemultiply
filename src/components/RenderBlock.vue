<template>
  <!-- Start Block -->
  <horizontal-line
    v-for="i in repeat"
    :key="i"
    :horizontalLines="horizontalLines"
  ></horizontal-line>
  <padding-line :horizontalLines="horizontalLines" />
  <!-- End Block -->
</template>

<script>
import PaddingLine from './PaddingLine.vue';
import HorizontalLine from './HorizontalLine.vue';

export default {
  props: { horizontalLines: Array, repeat: Number },
  components: { PaddingLine, HorizontalLine },
};
</script>
