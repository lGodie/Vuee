<template>
  <div>
    <h1>Formulario</h1>

    <form>
      <p>
        Nombre:
        <input type="text" name="nombre" size="40" />
      </p>
      <p>
        Año de nacimiento:
        <input type="number" name="nacido" min="1900" />
      </p>
      <p>
        Sexo:
        <input type="radio" name="hm" value="h" /> Hombre
        <input type="radio" name="hm" value="m" /> Mujer
      </p>
      <p>
        <button @click="GuardarFunc()">Guardar</button>
        <button @click="CloseFunc()">Cancelar</button>
      </p>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      HideNews: false
    };
  },
  methods: {
    GuardarFunc() {
      this.HideNews = true;
    },

    CloseFunc() {
      this.HideNews = false;
    }
  }
};
</script>

<style>
</style>
