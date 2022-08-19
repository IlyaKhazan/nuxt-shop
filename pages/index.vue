<template>
    <div :class="$style.container">
        <AddItemBlock />
        <ItemList />
    </div>
</template>

<script>
import AddItemBlock from "../components/AddItemBlock.vue";
import ItemList from "../components/ItemList.vue";
export default {components: {AddItemBlock, ItemList}};
</script>

<style lang="scss" module>
@import "../assets/scss/variables.scss";
.container {
    width: 100%;
    display: grid;
    grid-template-columns: 332px auto;
    gap: 16px;
    padding: 32px;

    @media (max-width: $mobile-width-only) {
        display: flex;
        flex-direction: column;
    }
}
</style>
