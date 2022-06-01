<template>
  <section class="catalog">
    <ul class="catalog__list">
      <li class="catalog__item"
          v-for="(products, index) in products" :key="index">
        <a class="catalog__pic" href="#">
          <img :src="products.image" :alt="products.title">
        </a>
        <h3 class="catalog__title">
          <a href="#">
            {{ products.title }}
          </a>
        </h3>
        <span class="catalog__price">
              {{ products.prise }}
            </span>
        <ul class="colors colors--black" >
          <li class="colors__item"
              v-for="(colorsRadio, index) in colorsRadio" :key="index" >
            <label :for="colorsRadio.index" class="colors__label">
              <input :id="colorsRadio.index" class="colors__radio sr-only"
                     type="radio" name="color-1" :value="products.index"
                     checked="">
              <span class="colors__value" :style="colorsRadio.color">
                  </span>
            </label>
          </li>
        </ul>
      </li>
    </ul>
  </section>
</template>

<script>
import colorsRadio from '@/data/colorsRadio';

export default {
  props: ['products'],
  data() {
    return {
      colorsRadio,
    };
  },
};
</script>
