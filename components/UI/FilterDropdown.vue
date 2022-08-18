<template>
    <div aria-label="Фильтр товаров" :class="{[$style.root]: true, [$style.opened]: areSortsVisible}">
        <p :class="$style.select" @click="areSortsVisible = !areSortsVisible">
            {{ selected.name }}
        </p>
        <div v-if="areSortsVisible" :class="$style.sorts">
            <p v-for="sort in sorts" :key="sort.value" :class="$style.sort" @click="selectSort(sort)">
                {{ sort.name }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: "FilterDropdown",
    props: {
        sorts: {
            type: Array,
            default() {
                return [];
            },
        },
        selected: {
            type: Object,
            default() {
                return {};
            },
        },
    },
    data() {
        return {
            areSortsVisible: false,
        };
    },
    methods: {
        selectSort(sort) {
            this.$emit("select", sort);
            this.areSortsVisible = !this.areSortsVisible;
        },
    },
};
</script>

<style lang="scss" module>
@import "~/assets/Scss/variables.scss";

.root {
    position: relative;
    line-height: 15px;
    font-size: 12px;
    padding: 10px 16px;
    width: 120px;
    background-color: $grey-200;
    border-radius: $border-radius--4;
    box-shadow: $shadow-secondary;
    cursor: pointer;
    &:hover {
        background-color: lighten($grey-100, 20%);
    }
    &:active {
        background-color: lighten($grey-100, 15%);
    }
    &::after {
        content: " ";
        position: absolute;
        height: 5px;
        width: 5px;
        border-bottom: 1px solid $grey-100;
        border-left: 1px solid $grey-100;
        display: block;
        transform: rotate(-45deg);
        top: 14px;
        right: 16px;
        transition: transform 0.3s ease-out;
    }
}

.opened {
    &::after {
        transform: rotate(135deg);
    }
}

.select {
    margin: 0;
    color: $grey-100;
}

.sort {
    margin: 0;
    padding: 10px 16px;
    background-color: $grey-200;
    &:hover {
        background-color: $grey-300;
    }
}

.sorts {
    position: absolute;
    width: 100%;
    top: 40px;
    left: 0;
    z-index: 1;
}
</style>
