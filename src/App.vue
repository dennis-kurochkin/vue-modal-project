<template>
  <h1>{{ title }}</h1>
  <button type="button" @click="toggleModal">Open modal</button>
  <Modal v-show="showingModal"
         :title="modal.title"
         :content="modal.content"
         theme="sale"
  />
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
      showingModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showingModal = !this.showingModal;
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
