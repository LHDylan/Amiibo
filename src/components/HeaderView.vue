<template>
  <section id="header">

    <!-- Logo -->
    <h1><a href="index.html">AmiiVue</a></h1>

    <!-- Nav -->
    <nav id="nav">
      <ul>
        <li>
          <router-link to="/">Home</router-link>
        </li>
        <!-- <li><a href="left-sidebar.html">Pokémons</a></li> -->
        <li>
          <router-link to="/liste">Liste Amiibo</router-link>
        </li>
      </ul>
    </nav>

  </section>
</template>

<script>
export default {
  name: 'HeaderView',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
