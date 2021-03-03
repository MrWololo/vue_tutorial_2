<template>
  <h1>{{ title }}</h1>
  <br />
  <!-- <input type="text" ref="name" />
  <button @click="handleClick">Click me</button> -->
  <div v-if="showModal">
    <Modal :theme="theme" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up</a>
        <a href="#">More Info</a>
      </template>

      <h1>{{ modalHeader }}</h1>
      <p>{{ modalText }}</p>
    </Modal>
  </div>
  <button @click="toggleModal('Bruh title', 'text', 'sale')">
    Switch Modal
  </button>
  <button @click="toggleModal('Bruh-less title', 'stonxt')">
    Switch Second Modal
  </button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My First Vue App",
      modalHeader: "",
      modalText: "",
      theme: "",
      showModal: false,
    };
  },
  methods: {
    // handleClick() {
    //   console.log(this.$refs.name);
    //   this.$refs.name.classList.add("active");
    //   this.$refs.name.focus();
    // },
    toggleModal(header, text, theme) {
      this.modalHeader = header;
      this.modalText = text;
      this.theme = theme;
      this.showModal = !this.showModal;
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
button {
  display: inline-flex;
  margin: 0 10px;
}
</style>
