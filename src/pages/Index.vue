<template>
  <div>
    <div class="page-header clear-filter" filter-color="orange">
      <parallax
        class="page-header-image"
        style="background-image:url('img/header.jpg')"
      >
      </parallax>
      <div class="container">
        <div class="content-center brand">
          <img class="n-logo" src="img/now-logo.png" alt="" />
          <h1 class="h1-seo">Now UI Kit.</h1>
          <h3>A beautiful Bootstrap 4 UI kit. Yours free.</h3>
        </div>
      </div>
    </div>
    
    <div class="section">
      <div class="container text-center">
        <div class="row justify-content-md-center">
          <div class="col-md-12 col-lg-8">
            <h2 class="title">Tables</h2>
            <h5 class="description">
              Tabel yang berisikan produk - produk dengan mencantumkan harga nya.
            </h5>
          </div>
        </div>
      </div>
    </div>
    <product-list></product-list>
    <signup-form></signup-form>
    <examples-section></examples-section>
  </div>
</template>
<script>
import { Parallax } from '@/components';
import SignupForm from './components/SignupForm';
import ExamplesSection from './components/ExamplesSection';
import ProductList from './components/ProductList.vue';

export default {
  name: 'index',
  bodyClass: 'index-page',
  components: {
    Parallax,
    SignupForm,
    ExamplesSection,
    ProductList,
  }
};
</script>
<style></style>
