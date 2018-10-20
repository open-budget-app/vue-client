<template>
  <main>
    <table class="table">
      <thead>
        <tr>
          <th>Name</th>
          <th>Budget</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="category in categories">
          <td>
            {{ category }}
          </td>
          <td>
            <input type="number" value="0">
          </td>
        </tr>
      
      </tbody>
    </table>

    <form v-on:submit.prevent="addCategory">
      <input autofocus type=text v-model="categoryName"></input>
      <button class="btn btn-primary ml-3">Add category</button>
    </form>
  </main>
</template>

<script>
export default {
  name: 'BudgetList',
  data() {
    return {
      categories: [],
      categoryName: '',
    }
  },
  methods: {
    addCategory() {
      if(this.categoryName.length > 0) {
        this.categories.push(this.categoryName);
        this.categoryName = '';
      }
    }
  }
}
</script>

