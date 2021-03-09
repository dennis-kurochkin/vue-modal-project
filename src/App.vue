<template>
  <h1>{{ title }}</h1>
  <button type="button" @click="toggleModal">Open modal</button>
  <Modal v-show="showModal"
         @close="toggleModal"
         theme="sale"
  >
    <template v-slot:default>
      <h1>{{ modal.title }}</h1>
      <p>{{ modal.content }}</p>
    </template>
    <template v-slot:links>
      <a href="#">Sign up</a>
      <a href="#">More info</a>
    </template>
  </Modal>
</template>

<script>
import Modal from './components/Modal';

export default {
  name: 'App',
  components: {
    Modal,
  },
  data() {
    return {
      title: 'My Second Vue App!',
      modal: {
        title: 'Custom modal heading',
        content: 'Custom modal content',
      },
      showModal: false,
    };
  },
  methods: {
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
</style>
