<template>
    <section :class="$style.root">
        <FilterDropdown :class="$style.filterDropdown" :selected="selected" :sorts="sorts" @select="sortSelect" />
        <div :class="$style.cards">
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
    </section>
</template>

<script>
import ItemCard from "./UI/ItemCard.vue";
import FilterDropdown from "./UI/FilterDropdown.vue";
export default {
    name: "ItemList",
    components: {FilterDropdown, ItemCard},
    data() {
        return {
            sorts: [
                {name: "По умолчанию", value: "default"},
                {name: "По мин. цене", value: "minPrice"},
                {name: "По макс. цене", value: "maxPrice"},
                {name: "По названию", value: "name"},
            ],
            selected: {name: "По умолчанию", value: "default"},
        };
    },
    methods: {
        sortSelect(sort) {
            this.selected = sort;
        },
    },
};
</script>

<style lang="scss" module>
.root {
    gap: 16px;
}

.cards {
    display: grid;
    gap: 16px;
    grid-template-columns: repeat(auto-fill, minmax(332px, 1fr));
}

.filterDropdown {
    margin-left: auto;
    margin-bottom: 16px;
}
</style>
