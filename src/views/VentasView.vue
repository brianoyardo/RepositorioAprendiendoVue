<template>
  <div class="about">
    <h1>Registro de Salida de Productos</h1>
    <p>Items a registrar = {{ store.count.length }}</p>
    <section>
      <form action="" @submit.prevent="handleSale()">
        <table>
          <thead>
            <tr>
              <th>Id</th>
              <th>Cantidad</th>
              <th>Precio</th>
              <th>Eliminar</th>
            </tr>
          </thead>
          <tbody v-if="store.count.length">
            <tr v-for="p in store.count">
              <td>{{ p.producto_Id }}</td>
              <td><input type="number" v-model="p.cantidad"></td>
              <td>{{ p.precio }}</td>
              <td><button @click="remove(p)">Quitar de la lista</button></td>
            </tr>
          </tbody>
        </table>
        <input type="submit" value="Enviar">
      </form>
    </section>
  </div>
</template>
<script setup>
import { store } from "./store"
const handleSale = () => {
  console.log(store.count)
}
const remove = (item) => {
  store.count.splice(store.count.indexOf(item),1)
}
</script>
<style>

</style>
