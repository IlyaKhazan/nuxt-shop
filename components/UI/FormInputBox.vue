<template>
  <div class="formInputBox">
    <label for="">Наименование товара</label><slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.formInputBox {
  display: flex;
  flex-direction: column;
  gap: 4px;
  font-size: 10px;
}
</style>
