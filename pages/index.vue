<template>
  <div class="container">
    <AddItemBlock />
    <ItemList />
  </div>
</template>

<script>
import AddItemBlock from "../components/AddItemBlock.vue";
import ItemList from "../components/ItemList.vue";
export default { components: { AddItemBlock, ItemList } };
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  width: 100%;
  display: flex;
  gap: 16px;
  flex-wrap: wrap;

  padding: 32px;
}
</style>
