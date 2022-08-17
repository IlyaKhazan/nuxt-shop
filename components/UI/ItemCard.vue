<template>
  <div class="itemCard">
    <img src="../../assets/img/item-image.png" alt="Фото товара" />
    <div class="itemCard__info">
      <p class="itemCard__title">Наименование товара</p>
      <p class="itemCard__description">
        Довольно-таки интересное описание товара в несколько строк.
        Довольно-таки интересное описание товара в несколько строк
      </p>
      <p class="itemCard__price">10 000р.</p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.itemCard {
  width: 332px;
  height: 423px;
  background-color: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
}

.itemCard__info {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 50%;
  padding: 16px;
}

.itemCard__title {
  font-size: 20px;
  font-weight: 600;
}

.itemCard__description {
  font-size: 16px;
}

.itemCard__price {
  font-size: 24px;
  font-weight: 600;
}
</style>
