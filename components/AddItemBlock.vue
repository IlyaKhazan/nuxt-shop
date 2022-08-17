<template>
  <div class="addItemBlock">
    <h1 class="addItemBlock__title">Добавление товара</h1>
    <form class="addItemBlock__form" action="">
      <FormInputBox><input type="text" /></FormInputBox>
      <FormInputBox><textarea rows="5"></textarea></FormInputBox>
      <FormInputBox><input type="text" /></FormInputBox>
      <FormInputBox><input type="text" /></FormInputBox>

      <FormButton />
    </form>
  </div>
</template>

<script>
import FormInputBox from "./UI/FormInputBox.vue";
import FormButton from "./UI/FormButton.vue";
export default { components: { FormInputBox, FormButton } };
</script>

<style scoped lang="scss">
input,
textarea {
  border: none;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  padding: 9px 9px 10px;
  resize: none;
}
.addItemBlock {
  width: 332px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.addItemBlock__form {
  display: flex;
  flex-direction: column;
  gap: 16px;
  background-color: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  min-height: 440px;
  padding: 24px;
}
.addItemBlock__title {
  font-size: 28px;
  color: #3f3f3f;
}
</style>
