<template>
  <div class="catalog-and-poppup">
    <div name="Каталог" class="catalog">
      <div class="burger">
        <span></span>
      </div>
      <a href="#" @click="poppUpCategory">Каталог</a>
    </div>
    <ul v-show="catalogClicked" class="catalog-popped-up-list">
      <li>Товар 1</li>
      <li>Товар 2</li>
      <li>Товар 3</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      catalogClicked: false,
    };
  },
  methods: {
    poppUpCategory() {
      this.catalogClicked = !this.catalogClicked;
    },
  },
};
</script>

<style lang="scss" scoped>
.catalog-and-poppup {
  display: flex;
  flex-direction: column;
  align-items: center;

  .catalog {
    background: #fed83d;
    border-radius: 4px;
    width: 116px;
    height: 40px;
    padding: 8px 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
    cursor: pointer;

    .burger {
      span,
      span::before,
      span::after {
        display: block;
        position: absolute;
        width: 20%;
        height: 2px;
        background-color: black;
      }

      span::before {
        content: "";
        top: -5px;
        width: 100%;
      }

      span::after {
        content: "";
        top: 5px;
        width: 100%;
      }
    }

    a {
      text-decoration: none;
      font-family: "Open Sans";
      font-style: normal;
      font-weight: 600;
      font-size: 14px;
      line-height: 24px;
      color: #050f19;
    }
  }

  .catalog-popped-up-list {
    position: absolute;
    top: 130px;
  }
}
</style>