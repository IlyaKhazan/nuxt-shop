<template>
    <div :class="$style.root">
        <label :class="$style.label" v-if="textarea">
            <span :class="$style.labelText">
                <span v-if="required" :class="$style.asterisk"></span>
                <slot></slot>
            </span>
            <textarea
                :class="[$style.input, $style.textarea]"
                :value="value"
                :placeholder="placeholder"
                @input="updInput"
            ></textarea>
        </label>
        <label :class="$style.label" v-else>
            <span :class="$style.labelText">
                <span v-if="required" :class="$style.asterisk"></span>
                <slot></slot>
            </span>
            <input :class="[$style.input]" :value="value" :placeholder="placeholder" @input="updInput" />
        </label>
    </div>
</template>

<script>
export default {
    name: "FormField",
    props: {
        type: {
            type: String,
            default: "text",
        },
        value: {
            type: [Number, String],
            default: "text",
        },
        placeholder: {
            type: String,
            default: "",
        },
        textarea: {
            type: Boolean,
            default: false,
        },
        labelId: {
            type: String,
            default: "",
        },
        required: {
            type: Boolean,
            default: false,
        },
    },
    methods: {
        updInput(evt) {
            this.$emit("input", evt.target.value);
        },
    },
};
</script>

<style lang="scss" module>
@import "../../assets/scss/variables.scss";

.root {
    margin-top: 16px;
    margin-bottom: 4px;
}

.label {
    display: flex;
    flex-direction: column;
    gap: 4px;
}

.labelText {
    position: relative;
    font-size: 10px;
    align-self: flex-start;
}

.input {
    border: none;
    box-shadow: $shadow-secondary;
    border-radius: $border-radius--4;
    padding: 9px 16px 10px;

    &::placeholder {
        font-size: 12px;
    }

    &:focus {
        outline: 1px solid $grey-100;
    }
}

.asterisk {
    position: absolute;
    border-radius: $border-radius--4;
    right: -5px;
    width: 4px;
    height: 4px;
    background-color: $pink;
}

.textarea {
    resize: none;
    min-height: 108px;
}
</style>
