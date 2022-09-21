<template>
  <div id="app">
    <div id="page-wrapper">
      <HeaderView />
      <router-view />
      <!-- 
        div id="main" mal découpé vis à vis du router-link donc elle est à deux endroits différents 
        div id="banner" en component mais pas placé
        date de release affiche des erreurs consoles consoles mais fonctionnent
      -->
      <FooterView />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderView from '@/components/HeaderView.vue';
import FooterView from '@/components/FooterView.vue';

export default {
  name: 'App',
  components: {
    HeaderView,
    FooterView
  }
}
</script>

<style>
@import '@/assets/css/main.css';
/* @import '@/assets/css/fontawesome-all.min.css'; */
</style>
