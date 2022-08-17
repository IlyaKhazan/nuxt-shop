<template>
  <div class="itemList">
    <ItemFilterBar />
    <div class="itemList__cards">
      <ItemCard />
      <ItemCard />
      <ItemCard />
      <ItemCard />
      <ItemCard />
      <ItemCard />
      <ItemCard />
      <ItemCard />
      <ItemCard />
      <ItemCard />
    </div>
  </div>
</template>

<script>
import ItemCard from "./UI/ItemCard.vue";
import ItemFilterBar from "./UI/ItemFilterBar.vue";
export default { components: { ItemCard, ItemFilterBar } };
</script>

<style scoped lang="scss">
.itemList {
  width: 1028px;
  gap: 16px;
}

.itemList__cards {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}
</style>
