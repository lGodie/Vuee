<template>
  <div id="App">
    <h1 v-show="HideNews">Noticias</h1>
    <div v-show="HideNews">
      <button @click="CloseNews()">Abrir</button>
      <div v-for=" MostrarNoticias in Noticias" v-bind:key="MostrarNoticias.id" class="news">
        <h1>{{ MostrarNoticias.title }}</h1>
        <p>{{ MostrarNoticias.body }}</p>
      </div>
    </div>
    <button @click="ShowNews()">Guardar</button>

    <div v-show="!HideNews">
      <Noticias1 ref="Noticias1" />
    </div>
    <div></div>
  </div>
</template>

<script>
import axios from "axios";
import Noticias1 from "./Noticias.vue";

export default {
  components: { Noticias1 },
  data() {
    return {
      Hello: "Hello world",
      Noticias: "",
      HideNews: false
    };
  },
  //Comment
  mounted() {
    this.NewFunc();
    this.getConsumir();
    // console.log(this.Hello);
  },

  methods: {
    NewFunc() {
      console.log("New function");
    },

    getConsumir() {
      axios.get("https://jsonplaceholder.typicode.com/posts").then(Response => {
        console.log(Response.data);
        this.Noticias = Response.data;
      });
    },

    OpenNews() {
      this.HideNews = true;
    },

    ShowNews() {
      this.HideNews = true;
    },

    CloseNews() {
      this.HideNews = false;
    }
  }
};
</script>

<style>
.news {
  border: 1px solid #999;
  padding: 20px;
  margin-bottom: 50px;
}
</style>
