<template>
  <tr>
    <td> <i class="fas fa-barcode"></i> {{ articulo.barra }}</td>
    <td>{{ articulo.nombre }}</td>
    <td>{{ Number(articulo.compra).toFixed(2) }}</td>
    <td>
      <button class="btn btn-primary" @click="AgregarCarrito()">
        <i class="fas fa-plus"></i>
      </button>
    </td>
  </tr>
</template>

<script>
export default {
  props: {
    articulo: {
      type: Object,
      default: () => { },
    },
  },
  methods: {
    AgregarCarrito() {
      this.$emit('AddCarrito', this.articulo);
    },
  },
};
</script>
