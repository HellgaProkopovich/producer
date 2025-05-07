<template>
  <!-- <Component
    :is="div"
    class="titles-container"
    :class=[alignTitles]
  ></Component> -->

  <div :class="['titles-container', alignTitlesContClass]">
    <h3 class="heading-thirdly">{{ subtitle }}</h3>
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
    alignTitlesContClass () {
      return this.align ===  'right'
      ? 'titles-container_align-right'
      : 'titles-container_align-left'
    }
  }
}
// defineProps({
//   title: String,
//   subtitle: String,
//   align: {
//     type: String,
//     default: 'left',
//     validator: (value) => ['left', 'right'].includes(value),
//   }
// })

// const alignTitlesContainer = {
//   left: 'titles-container_align-left',
//   right: 'titles-container_align-right'
// }[align]
</script>

<style>
.titles-container {
  padding: 10px;
}
.titles-container_align-left {
  text-align: left;
}
.titles-container_align-right {
  text-align: right;
}
</style>
