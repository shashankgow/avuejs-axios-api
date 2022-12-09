<template>
  <div id="app">
    <!-- <pre>{{ items }}</pre> -->
    <main>
      <section>
        <div class="container">
          <b-card
            title="Axios Api"
            sub-title="User Information"
            v-for="item in items"
            :key="item.id"
          >
            <b-card-text>
              <img
                :src="`https://avatars.dicebear.com/api/male/ +${item.name}.svg`"
                alt=""
              />
              name = {{ item.name }} <br />
              username= {{ item.username }} <br />
              Email = {{ item.email }} <br />
              Address = {{ item.address }} <br />
              Phone ={{ item.phone }} <br />
              Website = {{ item.website }} <br />
              
            </b-card-text>

            <b-card-text></b-card-text>

            <!-- <a href="#" class="card-link">Card link</a>
      <b-link href="#" class="card-link">Another link</b-link> -->
          </b-card>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      items: [],
    };
  },

  async mounted() {
    await axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((response) => (this.items = response.data));
  },
};
</script>

<style>
img{
  height: 100px;
}</style>
