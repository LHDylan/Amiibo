<template>
  <section id="main">
    <div class="container">

      <!-- Content -->
      <article class="box post">

        <header>
          <h2>Ma Collection</h2>
          <p>(ici le nombre d'amiibo)</p>
        </header>
        <p>
        <table>
          <tr>
            <th>Character</th>
            <th>game Series</th>
            <th>Action</th>
          </tr>
          <tr v-for="amiibo in amiibos" :key="amiibo.tail">
            <td>{{amiibo.character}}</td>
            <td>{{amiibo.gameSeries}}</td>
            <td><button @click="amiiboDetail(amiibo.tail)">voir</button></td>
          </tr>
        </table>
        </p>

      </article>

    </div>
  </section>
</template>

<script>
// @ is an alias to /src
import axios from 'axios';
const API_AMIIBO = 'https://www.amiiboapi.com/api/amiibo/'
// console.warn(API_AMIIBO);

export default {
  name: 'ListeView',
  data: () => ({
    amiibos: [],
  }),
  computed: {
  },
  methods: {
    amiiboDetail(amiiboTail) {
      this.$router.push({ name: 'detail', params: { amiiboTail: amiiboTail } })
    },

    async fetchAmiibos() {
      const AMIIBOS = await axios.get(API_AMIIBO);
      this.amiibos = AMIIBOS.data.amiibo;
      console.warn(this.amiibos);
    },
  },
  async created() {
    await this.fetchAmiibos();
  },
}
</script>
