<template>
  <div class="itemFilterBar"><FilterButton /></div>
</template>

<script>
import FilterButton from "./FilterButton.vue";
export default { components: { FilterButton } };
</script>

<style lang="scss">
.itemFilterBar {
  padding: 16px 0;
  display: flex;
  justify-content: end;
}
</style>
