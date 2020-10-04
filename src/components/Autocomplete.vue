<template>
  <div class="search">
    <div class="search__input">
      <input
        type="text"
        placeholder="Хочу найти..."
        v-model="search"
        @input="onChange"
      />
      <img src="/search.png" alt="" />
    </div>
    <div class="search__results">
      <ul v-show="isOpen" class="autocomplete-results">
        <li
          v-for="(result, i) in results"
          :key="i"
          @click="setResult(result)"
          class="autocomplete-result"
        >
          {{ search === "" ? "" : result }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: "",
      isOpen: false,
      results: [],
    };
  },
  props: {
    products: {
      type: Array,
      required: true
    },
  },
  methods: {
    onChange() {
      this.isOpen = true;
      this.filterResults();
    },
    filterResults() {
      this.results = this.products.filter(
        (item) => item.toLowerCase().indexOf(this.search.toLowerCase()) > -1
      );
    },
    setResult(result) {
      this.search = result;
      this.isOpen = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.search {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 52%;

  &__input {
    position: relative;
    display: flex;
    align-items: center;
    width: 100%;
    max-width: 526px;
    max-height: 40px;

    input {
      background: #ffffff;
      border: 1px solid #eceff1;
      box-sizing: border-box;
      border-radius: 4px;
      padding: 8px 24px;
      width: 100%;
      height: 40px;
    }

    img {
      position: absolute;
      right: 10px;
    }
  }

  &__results {
    position: absolute;
    top: 110px;
  }
  
  ul {
    li {
      cursor: pointer;
    }
  }
}
</style>