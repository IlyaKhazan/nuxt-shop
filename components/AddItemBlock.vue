<template>
    <section :class="$style.root">
        <h2 :class="$style.title">Добавление товара</h2>
        <form :class="$style.form" action="">
            <FormField :class="$style.formField" v-model="data.name" placeholder="Введите наименование товара" required
                >Наименование товара
            </FormField>
            <small :class="$style.error" v-if="!nameIsValid">Поле является обязательным</small>
            <FormField v-model="data.info" placeholder="Введите описание товара" textarea>Описание товара</FormField>
            <FormField v-model="data.imgSrc" placeholder="Введите ссылку" required>
                Ссылка на изображение товара
            </FormField>
            <small :class="$style.error" v-if="!imgSrcIsValid">Поле является обязательным</small>
            <FormField v-model="data.price" placeholder="Введите цену" required>Цена товара</FormField>
            <small :class="$style.error" v-if="!priceIsValid">Поле является обязательным</small>
            <FormButton
                :class="$style.formButton"
                text="Добавить товар"
                @submit.prevent="checkForm"
                :disabled="!formIsValid"
                :success="formIsValid"
            />
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
    computed: {
        nameIsValid() {
            return !!this.data.name;
        },
        imgSrcIsValid() {
            return !!this.data.imgSrc;
        },
        priceIsValid() {
            return !!this.data.price;
        },
        formIsValid() {
            return this.nameIsValid && this.imgSrcIsValid && this.priceIsValid;
        },
    },
    methods: {
        checkForm() {
            const formIsValid = this.nameIsValid && this.imgSrcIsValid && this.priceIsValid;

            if (formIsValid) {
                console.log("valid");
            } else {
                console.log("not valid");
            }
        },
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

.formField {
    margin-top: 0;
    input {
        border-color: $pink;
    }
}

.formButton {
    margin-top: 24px;
}

.form {
    display: flex;
    flex-direction: column;
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

.error {
    font-size: 8px;
    color: $pink;
}
</style>
