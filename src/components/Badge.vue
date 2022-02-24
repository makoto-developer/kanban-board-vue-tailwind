<template>
  <div
    class="px-4 h-5 rounded-full text-xs flex items-center"
    :class="`bg-${color}-200`"
  >
    <span class="w-2 h-2 rounded-full mr-1" :class="`bg-${color}-400`"></span>
    <span>
      <slot></slot>
    </span>
  </div>
</template>
<script>
export default {
  props: {
    color: {
      type: String,
      default: "Gray"
    }
  }
};
</script>
