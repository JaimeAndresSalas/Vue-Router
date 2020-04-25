<template>
  <div>
    <h1>Galeria de Fotos</h1>
    <router-link :to="{name:'fotos', params:{id: item}}" v-for="(item,index) of fotos" :key="index">
      <button class="btn btn-alert">Foto {{item}}</button>
    </router-link>

    <Imagen/>

    <button @click="home">Home</button>
    <button @click="regresar">Regresar</button>
    <button @click="siguiente">Siguiente</button>
  </div>
</template>

<script>
import Imagen from "@/components/Imagen.vue";

export default {
  components: {
    Imagen
  },
  data() {
    return {
      fotos: [1, 2, 3]
    };
  },
  methods: {
    home() {
      this.$router.push("/");
    },
    regresar(){
      this.$router.got(-1)
    },
    siguiente(){
      this.$router.got(1)
    }
  }
};
</script>


