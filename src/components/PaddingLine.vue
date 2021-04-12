<template>
  <line-block
    v-for="numLines in horizontalLines"
    :key="numLines"
    :numLines="numLines"
  />
  <div class="gap"></div>
</template>

<script>
import LineBlock from './LineBlock.vue';
export default {
  props: { horizontalLines: Array },
  components: { LineBlock },
};
</script>
