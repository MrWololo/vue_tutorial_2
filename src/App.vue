<template>
  <h1>{{ title }}</h1>
  <br>
  <!-- <input type="text" ref="name" />
  <button @click="handleClick">Click me</button> -->
  <div v-if="showModal">
    <Modal
      :header="modalHeader"
      :text="modalText"
      theme="sale"
      :showModal="showModal"
      @close="toggleModal"
    />
  </div>
  <button @click="toggleModal">Switch Modal</button>
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
      modalHeader: "Bruh",
      modalText: "jejox",
      showModal: false,
    };
  },
  methods: {
    // handleClick() {
    //   console.log(this.$refs.name);
    //   this.$refs.name.classList.add("active");
    //   this.$refs.name.focus();
    // },
    toggleModal() {
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
</style>
