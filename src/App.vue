<template>
  <h1>{{ title }}</h1>
  <button type="button" @click="toggleModal">Open modal</button>
  <button type="button" @click="togglePopup">Open popup</button>

  <teleport to=".modals">
    <Modal v-show="showModal"
           @close="toggleModal"
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
    <Modal v-show="showPopup"
           @close="togglePopup"
           theme="sale"
    >
      <template v-slot:default>
        <h1>Sale!</h1>
        <p>Some new sale thingy</p>
      </template>
      <template v-slot:links>
        <a href="#" @click="togglePopup">BUY</a>
      </template>
    </Modal>
  </teleport>

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
      showPopup: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    togglePopup() {
      this.showPopup = !this.showPopup;
    },
  },
};
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#app {
  margin-top: 60px;
}
</style>
