<template>
  <!-- <Component
    :is="div"
    class="titles-container"
    :class="[alignTitlesContClass]"
  ></Component> -->

  <div :class="['titles-container', alignTitlesContClass]">
    <h3 class="heading-thirdly text-gray">{{ subtitle }}</h3>
    <h2 class="heading-secondary">{{ title }}</h2>
  </div>
</template>

<script>
export default {
  name: 'BaseTitlesContainer',
  props: {
    title: String,
    subtitle: String,
    align: {
      type: String,
      default: 'left',
      validator: (value) => ['left', 'right'].includes(value),
    }
  },
  computed: {
    alignTitlesContClass() {
      return this.align ===  'right'
      ? 'titles-container_align-right'
      : 'titles-container_align-left'
    }
  }
}
</script>

<style>
/* .titles-container {
  margin: 28px 0 28px 0;
} */
.titles-container_align-left {
  text-align: left;
}
.titles-container_align-right {
  text-align: right;
}
</style>
