<template>
    <button
        :class="{
            [$style.button]: true,
            [$style.success]: success,
            [$style.disabled]: disabled,
        }"
        :type="type"
        @click="click"
    >
        {{ text }}
    </button>
</template>

<script>
export default {
    name: "FormButton",
    props: {
        text: {
            type: String,
            default: "",
        },
        type: {
            type: String,
            default: "text",
        },
        success: {
            type: Boolean,
            default: false,
        },
        disabled: {
            type: Boolean,
            default: false,
        },
    },
    methods: {
        click() {
            this.$emit("click");
        },
    },
};
</script>

<style lang="scss" module>
@import "../../assets/scss/variables.scss";

.button {
    background: $success;
    color: $white;
    background-color: $brown;
    border-radius: $border-radius--10;
    font-family: "Inter", sans-serif;
    font-weight: 600;
    padding: 10px;
    border: none;
    margin-top: auto;
    cursor: pointer;

    &:hover {
        background-color: lighten($brown, 10%);
    }
    &:active {
        background-color: darken($brown, 10%);
    }
}

.disabled {
    background: $grey-300;
    color: $grey-100;
    cursor: default;
    pointer-events: none;
}

.success {
    background: $success;
    color: $white;
    &:hover {
        background-color: lighten($success, 10%);
    }
    &:active {
        background-color: darken($success, 10%);
    }
}
</style>
