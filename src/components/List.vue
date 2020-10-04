<template>
  <div class="list-lable-and-list">
    <div class="list-lable" @click="poppUpList">
      <img src="/list.png" alt="" />
      <div>Список</div>
    </div>
    <ul class="list" v-show="listClicked">
      <li class="list__item">1</li>
      <li class="list__item">2</li>
      <li class="list__item">3</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listClicked: false,
    };
  },
  methods: {
    poppUpList() {
      this.listClicked = !this.listClicked;
    },
  },
};
</script>

<style lang="scss" scoped>
.list-lable-and-list {
  display: flex;
  flex-direction: column;
  align-items: center;

  .list-lable {
    display: flex;
    align-items: center;
    width: 111px;
    justify-content: space-between;
    padding: 8px 16px;
    background: #fafbfc;
    border: 1px solid #eceff1;
    box-sizing: border-box;
    border-radius: 4px;
    position: relative;
    cursor: pointer;
  }

  .list {
    position: absolute;
    top: 120px;
  }
}
</style>