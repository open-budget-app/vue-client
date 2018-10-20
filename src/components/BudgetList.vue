<template>
  <main>
    <table class="table">
      <thead>
        <tr>
          <th>Name</th>
          <th>Budget</th>
          <th>Activity</th>
          <th>Available</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="category in categories">
          <td>
            {{ category.name }}
          </td>
          <td>
            <input type="number" value="0">
          </td>
          <td>
            0
          </td>
          <td>
            <span class="badge badge-success">
              321
            </span>
          </td>
        </tr>
      </tbody>
    </table>

    <form v-on:submit.prevent="addCategory">
      <input autofocus type=text v-model="newCategory.name"></input>
      <button class="btn btn-primary ml-3">Add category</button>
    </form>
  </main>
</template>

<script>
export default {
  name: 'BudgetList',
  data() {
    return {
      categories: [
        {
          name: 'Boodschappen',
          budgeted: 200,
        },
        {
          name: 'Spotify',
          budgeted: 10,
        },
      ],
      newCategory: {
        name: '',
        budgeted: 0,
      }
    }
  },
  methods: {
    addCategory() {
      if(this.newCategory.name.length > 0) {
        this.categories.push({
          name: this.newCategory.name,
          budgeted: 0,
        });
        this.newCategory.name = '';
      }
    }
  }
}
</script>

