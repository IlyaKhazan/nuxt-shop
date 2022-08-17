<template>
  <div class="itemFilterBar"><FilterButton /></div>
</template>

<script>
import FilterButton from "./FilterButton.vue";
export default { components: { FilterButton } };
</script>

<style lang="scss">
.itemFilterBar {
  padding-bottom: 16px;
  display: flex;
  justify-content: end;
}
</style>
