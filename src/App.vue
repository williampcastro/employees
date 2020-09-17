<template>
  <div id="app">

    <h1>Employess</h1>

    <table>
      <thead>
        <tr>
          <th>Name</th>
          <th>E-mail</th>
          <th>Sector</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>

        <tr>

          <td>William</td>
          <td>wila@email.com</td>
          <td>Product</td>

          <td>

            <button>Editar</button>
            <button>Remover</button>

          </td>
        </tr>
      </tbody>
    </table>


  </div>
</template>

<script>
export default {
  name: 'app',
  data () {

  }
}
</script>

<style lang="scss">

</style>
