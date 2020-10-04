<template>
  <div>
    <div class="menu">
      <div class="content">
        <div class="menu-content">
          <Logo />
          <Catalog />
          <Autocomplete :products="products" />
          <List />
          <Avatar />
        </div>
      </div>
    </div>
    <div></div>
  </div>
</template>

<script>
import Autocomplete from "./Autocomplete";
import Catalog from "./Catalog";
import List from "./List";
import Avatar from "./Avatar";
import Logo from "./Logo";

export default {
  name: "Menu",
  components: {
    Logo,
    Autocomplete,
    Catalog,
    List,
    Avatar,
  },
  data() {
    return {
      products: ["item1", "item2", "item3"],
    };
  },
};
</script>

<style lang="scss" scoped>
.menu {
  width: 100%;
  padding: 18px 0;
}

.menu-content {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
