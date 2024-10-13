<template>
  <h1> {{ msg }} </h1>
  <p>Welcome...</p>
  
  <!-- First Modal -->
  <div v-if="showModal1">
    <Modal theme="sale" @close="toggleShowModal1">
      <template v-slot:links>
        <a href="facebook.com">Facebook</a>
        <a href="twitter.com">Twitter</a>
      </template>
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </Modal>
  </div>

  <!-- Second Modal -->
  <div v-if="showModal2">
    <Modal @close="toggleShowModal2">
      <template v-slot:links>
        <a href="youtube.com">YouTube</a>
        <a href="linkedin.com">LinkedIn</a>
      </template>
      <input type="text" placeholder="Enter your name">
      <input type="email" placeholder="Enter your email">
    </Modal>
  </div>

  <br>
  <button @click="toggleShowModal1">Show Modal</button>
  <br>
  <button @click="toggleShowModal2">Toggle Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      header: 'Sign Up',
      text: 'This is the Text',
      showModal1: false,  // Control for the first modal
      showModal2: false   // Control for the second modal
    }
  },
  methods: {
    toggleShowModal1() {
      this.showModal1 = !this.showModal1;  // Toggles first modal visibility
    },
    toggleShowModal2() {
      this.showModal2 = !this.showModal2;  // Toggles second modal visibility
    }
  }
}
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

h1 {
  border-bottom: 1px solid #000000;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
