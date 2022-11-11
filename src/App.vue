<template>
  <header>
    <h1>Events</h1>
  </header>
  <section id="app">
    <h2>Event Practice</h2>
    <!-- 1) Show an alert (any text of your choice) when the button is pressed -->
    <button @click="showAlert">Show Alert</button>
    <hr />
    <!-- 2) Register the user input on "keydown" and output it in the paragraph (hint: event.target.value helps) -->
    <input
      type="text"
      placeholder="What's your favorite food?"
      @keydown="findFood"
    />
    <p>Food of choice: {{ food }}</p>
    <hr />
    <!-- 3) Repeat 2) but only output the entered value if the ENTER key was pressed -->
    <input
      placeholder="What's your favorite city?"
      type="text"
      @keyup.enter="findCity"
    />
    <p>City: {{ city }}</p>
  </section>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data() {
    return {
      food: '',
      city: '',
    };
  },
  methods: {
    findFood(event) {
      this.food = event.target.value;
    },
    findCity(event) {
      this.city = event.target.value;
    },
    showAlert(event) {
      event.preventDefault();
      alert('Alert message');
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
