<template>
  <div>
    <!-- render dynamic bloks from `Landingpage` content type -->
    <slot name="bloks" />
  </div>
</template>
<script>
export default {
  props: {
    blok: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>
