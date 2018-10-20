<template>
  <div class="row">
    <div class="col-8">
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
            <input min="0" type="number" v-model="category.budgeted">
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
    </div>

    <div class="col-4 p-4 vh-100" style="background: #007bff1a none repeat scroll 0% 0%;">
      <div class="mb-3">
        <h4>TOTAL BUDGETED</h4>
        {{ totalBudgeted }}
      </div>
      <div class="mb-3">
        <h4>TOTAL ACTIVITY</h4>
        -
      </div>
      <div class="mb-3">
        <h4>TOTAL AVAILABLE</h4>
        -
      </div>
      <div class="mb-3">
        <h4>TOTAL INFLOWS</h4>
        -
      </div>
    </div>
   
  </div>
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
  },
  computed: {
    totalBudgeted() {
      let total = this.categories.reduce((cat, val) => parseInt(cat) + parseInt(val.budgeted), 0)
      return '€' + total;
    }
  }
}
</script>

