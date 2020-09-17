<template>
  <div id="app">

    <h1>Employees</h1>

    <table v-if="employees.length">
      <thead>
      <tr>
        <th>#</th>
        <th>Name</th>
        <th>E-mail</th>
        <th>Sector</th>
        <th>Actions</th>
      </tr>
      </thead>
      <tbody>

      <tr v-for="(employee, index) in employees">

        <td> {{ index + 1 }}</td>
        <td>{{ employee.name ? employee.name : '--' }}</td>
        <td>{{ employee.phoneNumber ? employee.phoneNumber : '--' }}</td>
        <td>{{ employee.email ? employee.email : '--' }}</td>
        <td>{{ employee.sector ? employee.sector : '--' }}</td>

        <td>

          <button :id="'button_update_' + index" v-show="!buttonSaveIsAble" @click="showButtonSave()">Update</button>
          <button :id="'button_save_' + index" v-show="buttonSaveIsAble" @click="updateEmployee()">Save</button>
          <button :id="'button_remove_' + index" @click="removeEmployee(index)">Remove</button>

        </td>
      </tr>
      </tbody>
    </table>

    <div v-else> Not employees registered!</div>

  </div>
</template>

<script>

const invertBooleanValue = function (data) {
  return !data;
}

const employees = [];
employees.push( { name: 'Will_1', phoneNumber: '9 9999-1111', email: 'will@will.com', sector: 'DEV' })
employees.push( { name: 'Will_2', phoneNumber: '9 9999-1111', email: 'will@will.com', sector: null })
employees.push( { name: 'Will_3', phoneNumber: null, email: 'will@will.com', sector: 'DEV' })


export default {
  name: 'app',

  methods: {
    removeEmployee: function (index) {
      this.$delete (this.employees, index)
    },
    updateEmployee: function () {
      this.buttonSaveIsAble = true;
      this.buttonSaveIsAble = invertBooleanValue(this.buttonSaveIsAble)
    },
    showButtonSave: function () {
      this.buttonSaveIsAble = invertBooleanValue(this.buttonSaveIsAble)
    },
  },

  data () {
    return {
      buttonSaveIsAble: false,
      employees,
    }
  }

}
</script>

<style lang="scss">

</style>
