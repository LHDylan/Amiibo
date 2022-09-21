<template>
  <section id="main">
    <div class="container">
      <div class="row">
        <div class="col-4 col-12-medium">

          <!-- Sidebar -->
          <section class="box">
            <header>
              <h3>Infos</h3>
            </header>
            <p> amiiboSeries: <b>{{amiibo.amiiboSeries}}</b> <br />
              character: {{amiibo.character}}<br />
              gameSeries: {{amiibo.gameSeries}}<br />
              type: {{amiibo.type}}
            </p>

          </section>
          <section class="box">
            <header>
              <h3>Dates sorties</h3>
            </header>

            <ul class="divided">
              <li>au: {{amiibo.release.au}}</li>
              <li>eu: {{amiibo.release.eu}}</li>
              <li></li>
              <li></li>
            </ul>
          </section>

        </div>
        <div class="col-8 col-12-medium imp-medium">

          <!-- Content -->
          <article class="box post">
            <a href="#" class="featured"><img
                src="https://raw.githubusercontent.com/N3evin/AmiiboAPI/master/images/icon_04610001-01610502.png"
                alt="" /></a>
            <header>
              <h2>{{amiibo.character}}</h2>
              <p>{{amiibo.type}}</p>
            </header>
          </article>

        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
// @ is an alias to /src

export default {
  name: 'DetailView',
  components: {
  },
  data: () => ({
    amiibo: {}
  }),
  async created() {
    const { amiiboTail } = this.$route.params;
    const API_AMIIBO_DETAIL = 'https://www.amiiboapi.com/api/amiibo/?tail=' + amiiboTail;
    const thisAmiibo = await axios.get(API_AMIIBO_DETAIL);

    console.warn(thisAmiibo.data.amiibo[0]);
    this.amiibo = thisAmiibo.data.amiibo[0];

    // this.amiiboAu = thisAmiibo.data.amiibo[0].release[0];
    // console.warn(thisAmiibo.data.amiibo[0].release.au);
  }
}
</script>
