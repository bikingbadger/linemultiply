<template>
  <horizontal-line-block
    v-for="numLines in horizontalLines"
    :key="numLines"
    :numLines="numLines"
    lineType="horizontal"
  />
  <div class="line-horizontal"></div>
</template>

<script>
import HorizontalLineBlock from './LineBlock.vue';

export default {
  props: { horizontalLines: Array },
  components: { HorizontalLineBlock },
};
</script>
