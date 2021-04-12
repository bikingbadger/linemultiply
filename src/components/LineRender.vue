<template>
  <input type="number" name="firstNumber" id="firstNumber" v-model="num1" />
  <input type="number" name="secondNumber" id="secondNumber"  v-model="num2" />

  <div class="box" :style="gridTemplate">
    <padding-line :horizontalLines="horizontalLines" />
    <render-block
      v-for="vertical in verticalLines"
      :key="vertical"
      :horizontalLines="horizontalLines"
      :repeat="vertical"
    />
  </div>
</template>

<script>
import PaddingLine from './PaddingLine.vue';
import HorizontalLine from './HorizontalLine.vue';
import RenderBlock from './RenderBlock.vue';

export default {
  components: { PaddingLine, HorizontalLine, RenderBlock },
  data() {
    return { num1: 12, num2: 13 };
  },
  computed: {
    verticalLines() {
      return Array.from(String(this.num2), Number);
    },
    horizontalLines() {
      return Array.from(String(this.num1), Number);
    },
    gridTemplate() {
      return {
        gridTemplateColumns: `2fr repeat(${this.horizontalLines[0]}, 1fr) 10fr repeat(${this.horizontalLines[1]}, 1fr) 2fr`,
        gridTemplateRows: `2fr repeat(${this.verticalLines[0]}, 1fr) 10fr repeat(${this.verticalLines[1]}, 1fr) 2fr`,
      };
    },
  },
};
</script>

<style>
.box {
  display: grid;
  /* grid-template-columns: 2fr repeat(5, 1fr) 10fr repeat(3, 1fr) 2fr;
  grid-template-rows: 2fr repeat(2, 1fr) 10fr repeat(3, 1fr) 2fr; */
  grid-auto-flow: row;
  height: 400px;
  width: 400px;
  transform: rotate(-45deg);
  margin: 5rem auto;
}

.line-vertical {
  border-left: 1px solid blue;
}
.line-horizontal {
  border-top: 1px solid blue;
}
</style>
