<template>
  <v-container class="mb-5">
    <h1 class="text-dark">Calories Store</h1>
    <br>

    <v-text-field label="Enter Item Name" v-model="name"></v-text-field>
    <v-text-field label="Enter Calories" type="number" v-model="calories"></v-text-field>

    <div class="me-3">
      <v-btn class="me-3" color="black" @click="AddNewItem">Add Item</v-btn>
      <v-btn class="me-3" color="black" @click="DeleteItem" variant="outlined">Delete</v-btn>
      <button class="btn btn-primary">Click Again</button>
    </div>
    
    <hr class="mb-5 mt-5">

    <v-table class="mt-5" theme="dark" density="compact">
      <thead>
        <tr>
          <th class="text-left">
            Name
          </th>
          <th class="text-left">
            Calories
          </th>
          <th class="text-left">
            Result
          </th>
        </tr>
      </thead>
      <tbody>
        <!-- Looping -->
        <tr
          v-for="item in desserts"
          :key="item.name"
        >
          <td>{{ item.name }}</td>
          <td>{{ item.calories }}</td>
          <!-- Check condition in attribute -->
          <td v-if="item.calories<250">Good</td>
          <td v-else>Not Good</td>
        </tr>
      </tbody>
    </v-table>



  </v-container>
</template>

<script>

export default {
  name: 'HelloWorld',

  data: () => ({
    name: "",
    calories: "",
    desserts: [
          {
            name: 'Frozen Yogurt',
            calories: 159,
          },
          {
            name: 'Ice cream sandwich',
            calories: 237,
          },
          {
            name: 'Eclair',
            calories: 262,
          },
          {
            name: 'Cupcake',
            calories: 305,
          },
          {
            name: 'Gingerbread',
            calories: 356,
          }
        ]

  }),

  methods: {
    AddNewItem() {
      this.desserts.push({name:this.name, calories: this.calories});
    },

    DeleteItem() {
      this.desserts.pop({name:this.name, calories: this.calories});
    },

  }

}
</script>
