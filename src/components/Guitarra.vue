<template>
  <div class="col-md-6 col-lg-4 my-4 row align-items-center">
    <div class="col-4">
      <img class="img-fluid" :src="'/img/'+guitarra.imagen+'.jpg'" :alt="'imagen guitarra'+guitarra.nombre" />
    </div>
    <div class="col-8">
      <h3 class="text-black fs-4 fw-bold text-uppercase">
        {{ guitarra.nombre }}
      </h3>
      <p>{{ numero }}</p>
      <p>
        {{ guitarra.descripcion }}
      </p>
      <p class="fw-black text-primary fs-3">${{ guitarra.precio }}</p>
      <button type="button" class="btn btn-dark w-100" @click="agregarCarrito(guitarra)">
        Agregar al Carrito
      </button>
    </div>
  </div>
  <!-- FIN GUITARRA -->
</template>

<script setup>
//Vue
import { ref } from 'vue';

const numero = ref(0);

const props = defineProps({
  guitarra: {
    type: Object,
    required: true,
  },
});

const emits = defineEmits(["agregar-carrito"]);

const agregarCarrito = (guitarra) => {
  emits('agregar-carrito', guitarra);
}
</script>
