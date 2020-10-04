<template>
  <header class="header">
    <div class="content">
      <div class="header-content">
        <div class="header-content__left">
          <div class="location">
            <img src="/location.png" alt="" />
            <div>Волгоградская область</div>
          </div>
        </div>
        <div class="header-content__right">
          <nav>
            <ul class="list">
              <li class="list__item">
                <a href="">Тендеры</a>
              </li>
              <li class="list__item">
                <a href="">База подрядчиков</a>
              </li>
              <li class="list__item">
                <a href="#">
                  <select name="Другие сервисы" id="" v-model="selected">
                    <option value="" disabled>Другие сервисы</option>
                    <option value="">Второй сервис</option>
                  </select>
                </a>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      selected: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  padding: 6px 0;
  background: #fafbfc;
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 20px;
  color: #708598;
}

.header-content {
  display: flex;
  align-items: center;
  width: 100%;
  justify-content: space-between;
}

.location {
  display: flex;

  div {
    margin-left: 8px;
  }
}

.list {
  display: flex;
  align-items: center;
  width: 100%;

  &__item a {
    text-decoration: none;
    color: #708598;

    select {
      border: none;
      font-family: "Open Sans";
      font-style: normal;
      font-weight: normal;
      font-size: 12px;
      line-height: 20px;
    }
  }

  &__item + &__item {
    margin-left: 24px;
  }
}
</style>