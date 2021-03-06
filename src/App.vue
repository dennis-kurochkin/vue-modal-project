<template>
  <h1>{{ title }}</h1>
  <button type="button" @click="toggleModal">Open modal</button>
  <Modal v-show="showingModal"/>
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
      title: 'Second Vue App BABYYYYYYY',
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
