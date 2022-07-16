<template>
   <p>Welcome...</p>
   <div v-if="showModal">
      <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/>
   </div>
   <button class="btn" @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      header: 'Sign up for the giveaway',
      text: 'Grab your ninja price for half price promo',
      showModal: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
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
  .btn {
    padding: 15px 25px;
    background-color: rgb(4, 109, 56);
    border: 0;
    color: #fff;
    font-size: 24px;
    border-radius: 10px;
    cursor: pointer;
  }
</style>
