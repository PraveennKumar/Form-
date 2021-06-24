<template>
  <div>
    <Form>
      <template class="head" v-slot:head>
        <h1>Vue js projects</h1>
        <h2>Form</h2>
      </template>
      <template class="main" v-slot:main>
        <form v-on:submit="onSubmit">
          <p>Name:</p>
          <input
            type="text"
            placeholder="name"
            name="name"
            id="naam"
            v-model="name"
          /><br />
          <br />
          <p>Age:</p>
          <input
            type="number"
            placeholder="age"
            id="Umar"
            v-model="age"
          /><br />
          <br />
          <button type="Submit">Submit</button>
          <p v-if="msg">{{ msg }}</p>
        </form>
      </template>
      <template v-slot:footer>
        <h3>Copyright 2021-Praveen</h3>
      </template>
    </Form>
  </div>
</template>

<script>
import Form from "./components/Form.vue";

export default {
  name: "App",
  components: {
    Form,
  },
  data() {
    return {
      name: "",
      age: "",
      msg: "",
    };
  },
  methods: {
    onSubmit: function (e) {
      e.preventDefault();
      console.log(this.name, this.age);
      if (!this.name || !this.age) {
        this.msg = "user name and  age are compulsory to filled";
      } else {
        this.msg = "Form submitted successfully";
      }
    },
  },
};
</script>

<style scoped>
h1 {
  color: white;
  background-color: grey;
  width: 250px;
}
</style>
