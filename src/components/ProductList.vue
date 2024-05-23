<template>
  <div class="product-list">
    <div class="flex top-information">
      <h1>Письменные столы</h1>
      <myInput @search="searchProducts" />
      <!--input 
        type="text" 
        class="search"
        v-model="searchText"
      -->
      <!-- v-modal слушает @input и пробрасывает значение в :value -->
      <!--input 
        type="text" 
        class="search"
        :value="searchText"
        @input="searchText = $event.target.value"
      -->
      {{ searchText }}
      <!--button>
        Найти
      </button-->
    </div>
    
    <ul class="list-default flex">
      <li
        v-for="(product, index) in products"
        :key="index"
      >
        <product-card
          :title="product.title"
          :price="product.price"
          :img-url="product.imgUrl"
          :count="product.count"
          @addToBasket="addToBasket(index)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import ProductCard from './ProductCard'
import MyInput from './MyInput'

export default {
  name: 'ProductList',
  components: { ProductCard, MyInput },
  data() {
    return {
      searchText: '',
      products: [
        {
          title: 'Стол Jim',
          price: 19999,
          imgUrl: 'https://hoff.ru/upload/iblock/6e8/6e8c9aae3cd7fba67e53912cc4f503ee.jpg',
          count: 30
        },
        {
          title: 'Стол Monako',
          price: 17199,
          imgUrl: 'https://hoff.ru/upload/iblock/377/377bd200020ac7767e6ce78958ecbba6.jpg',
          count: 20
        },
        {
          title: 'Стол с двумя ящиками Кварт MD 768',
          price: 10999,
          imgUrl: 'https://hoff.ru/upload/iblock/1cc/1ccb33b50e3e9cfa08629bf455e41855.jpg',
          count: 23
        }
      ]
    }
  },
  methods: {
    addToBasket(index) {
      console.log(index)
    },
    searchProducts(searchText) {
      console.log(`Загрузить товары ${searchText}`);
    }
  }
}
</script>

<style scoped>
  li {
    margin-right: 20px;
    margin-bottom: 22px;
  }
  .top-information {
    align-items: center;
  }
  h1 {
    margin-bottom: 0;
  }
  button {
    background-color: rgb(221, 56, 56);
    color: #fff;
    border: none;
    border-radius: 4px;
    padding: 8px 14px;
    display: block;
    cursor: pointer;
    margin-left: 10px;
  }
</style>
