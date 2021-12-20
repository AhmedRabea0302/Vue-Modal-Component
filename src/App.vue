<template>
  <h1>{{title}}</h1>

  <teleport to=".modals" v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Signup Now</a>
        <a href="#">More Info</a>
      </template>
      <h1>Athletes Never Surrender</h1>
      <p>Choose Youe Equipment from a big stock</p>
    </Modal>
  </teleport>

  <teleport to=".modals" v-if="showModal2">
    <Modal @close="toggleModal2">
      <h1>Sand Bag</h1>
      <p>Sand Bag that weights 45 KG</p>

      <template v-slot:links>
        <a href="#">Love Product</a>
        <a href="#">More Info</a>
      </template>
    </Modal>
  </teleport>

  <p>Welcome ...</p>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModal2">Open Sand Bag Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',

  components: {
    Modal,
  },

  data() {
    return {
      title: 'Hello from the other side',
      header: 'Hello From props',
      text: 'paragarph text',
      showModal: false,
      showModal2: false
    }
  }, 
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
      console.log(this.showModal)
    },

    toggleModal2() {
      this.showModal2 = !this.showModal2;
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

.active {
  border: 2px solid green;
}
</style>
