<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to=".modals"  v-if="showModal">
    <Modal  theme="sale" @close="toggleModal" >
      <template v-slot:links>
       <a href="#">Sign up now</a>      
       <a href="#">More info</a>      
      </template>
      <h1>Hidden Cat Giveaway!!</h1>
      <p>Grab your swag for half price!!</p>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo" >
        <h1>Why are you opening this?</h1>
        <p>Check the first modal and BUY</p>          
    </Modal>
  </div>

  <button @click="toggleModal">Open modal</button>
  <button @click="toggleModalTwo">Open second modal</button>
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components:{ Modal},
  data(){
    return {
      title: 'My first Vue App :)',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
      toggleModal(){
        this.showModal = !this.showModal
      },
      toggleModalTwo(){
        this.showModalTwo = !this.showModalTwo
      }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
button{
  margin-right: 10px;
}
</style>
