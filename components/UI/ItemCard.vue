<template>
    <div :class="$style.root">
        <img src="../../assets/img/item-image.png" width="332px" height="200px" alt="Фото товара" />
        <div :class="$style.info">
            <p :class="$style.title">Наименование товара</p>
            <p :class="$style.description">
                Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в
                несколько строк
            </p>
            <p :class="$style.price">10 000 руб.</p>
        </div>
        <button :class="$style.delCardBtn">
            <Icon />
        </button>
    </div>
</template>

<script>
import Icon from "~/assets/img/del-btn.svg?inline";
export default {name: "ItemCard", components: {Icon}};
</script>

<style lang="scss" module>
@import "../../assets/scss/variables.scss";

.root {
    position: relative;
    max-width: 332px;
    background-color: $grey-200;
    box-shadow: $shadow-primary;
    border-radius: 4px;
    color: $black;
    cursor: pointer;

    &:hover > .delCardBtn {
        display: block;
    }
}

.info {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 50%;
    max-width: 332px;
    padding: 16px 16px 24px;
}

.title {
    font-size: 20px;
    font-weight: 600;
}

.description {
    font-size: 16px;
    padding-top: 16px;
    padding-bottom: 16px;
}

.price {
    font-size: 24px;
    font-weight: 600;
    padding-top: 16px;
}

.delCardBtn {
    display: none;
    position: absolute;
    background-repeat: no-repeat;
    background-color: $pink;
    border-radius: $border-radius--10;
    width: 32px;
    height: 32px;
    padding: 0;
    border: none;
    right: -8px;
    top: -8px;
    cursor: pointer;

    &:hover {
        background-color: lighten($pink, 10%);
    }

    &::after {
        content: " ";
        position: absolute;
        background-image: url("../../assets/img/del-btn.svg");
        height: 16px;
        width: 16px;
        display: block;
        top: 8px;
        left: 8px;
    }
}
</style>
