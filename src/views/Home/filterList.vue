<template>
  <div class="filterList">
    <div class="input-group input-group-lg">
      <input v-model="keywords" placeholder="Search..." type="text" class="form-control">
    </div>
    <table class="table table-bordered">
      <thead class="thead-dark">
        <tr scope="row">
          <th scope="col">Name</th>
          <th scope="col">Sku</th>
          <th scope="col">Renewal Date</th>
          <th scope="col">Recurring sell (incl VAT)</th> 
        </tr>
      </thead>
      <tbody>
        <tr scope="row" v-for="item in ListData" :key="item.id">
          <td>{{ item.name }}</td>
          <td>{{ item.sku }}</td>
          <td>{{ item.sku }}</td>
          <td>{{ item.sell_recurring_incl_vat }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import * as list from '../../assets/data.json'

export default {
  name: 'filterList',
  data: () => {
    return {
      keywords: '',
      list
    }
  },
  computed: {
    ListData () {
      return this.list.data.filter(item => item.name.toLowerCase().includes(this.keywords.toLowerCase()) || item.sku.toLowerCase().includes(this.keywords.toLowerCase()))
    }
  }
}
</script>