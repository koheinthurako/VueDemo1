<template>
  <v-container>
    <h1 class="text-primary">Hello World</h1>
    <br>
    {{ msg }}
    <br>
    <br>
    <v-btn v-on:click="clickBtn()">Click here!</v-btn>
  </v-container>
</template>

<script>

export default {
  name: 'HelloWorld',

  data: () => ({
    msg: "Hi how are you?"
  }),

  methods: {
    clickBtn() {
      console.log("Hello World!")
      this.msg = "You clicked btn!"
    }
  }

}
</script>
