<template>
    <section :class="$style.root">
        <h2 :class="$style.title">Добавление товара</h2>
        <form :class="$style.form" action="">
            <FormField v-model="data.name" placeholder="Введите наименование товара" required
                >Наименование товара
            </FormField>
            <FormField v-model="data.info" placeholder="Введите описание товара" textarea>Описание товара</FormField>
            <FormField v-model="data.imgSrc" placeholder="Введите ссылку" required>
                Ссылка на изображение товара
            </FormField>
            <FormField v-model="data.price" placeholder="Введите цену" required>Цена товара</FormField>
            <FormButton text="Добавить товар" @click="click" :disabled="true" />
        </form>
    </section>
</template>

<script>
import FormField from "./UI/FormField.vue";
import FormButton from "./UI/FormButton.vue";

export default {
    name: "AddItemBlock",
    components: {FormField, FormButton},
    data() {
        return {
            data: {name: "", info: "", imgSrc: "", price: ""},
        };
    },
    methods: {
        click() {},
    },
};
</script>

<style lang="scss" module>
@import "../assets/scss/variables.scss";

.root {
    width: 332px;
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.form {
    display: flex;
    flex-direction: column;
    gap: 16px;
    background-color: $grey-200;
    box-shadow: $shadow-primary;
    border-radius: 4px;
    min-height: 440px;
    padding: 24px;
}

.title {
    font-size: 28px;
    color: $black;
}
</style>
