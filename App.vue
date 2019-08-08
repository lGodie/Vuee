<template>
  <div>
    <table>
      <tbody>
        <tr v-for=" MostrarNoticias in Noticias" v-bind:key="MostrarNoticias.id">
          <td>{{ MostrarNoticias.userId }}</td>
          <td>{{ MostrarNoticias.id }}</td>
          <td>{{ MostrarNoticias.title }}</td>
          <td>{{ MostrarNoticias.body }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      Hello: "Hello world",
      Noticias: ""
    };
  },

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
    }
  }
};
</script>

<style>
</style>
