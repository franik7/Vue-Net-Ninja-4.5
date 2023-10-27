<template>
<h1>{{ title }}</h1>
<p>Welcome...</p>
<!--Change div to teleport-->
<teleport to = ".modals" v-if="showModal">
  <Modal theme="" @close="toggleModal">
    <template v-slot:links>
      <a href = "#">Sign up now</a>
      <a href = "#">more info</a>
    </template>
    <h1>Ninja Giveaway!</h1>
    <p>Grab your Ninja swag!</p>
  </Modal>
</teleport>
<button @click = "toggleModal">open modal (alt)</button>

<br><br>

<teleport to = ".modals" v-if="showModalTwo">
  <Modal theme="sale" @close="toggleModalTwo">
    <template v-slot:links>
      <a href = "#">Click Me</a>
      <a href = "#">privacy policy</a>
    </template>
    <h1>Sign up for newsletter!</h1>
    <p>Read our privacy policy</p>
  </Modal>
</teleport>
<button @click = "toggleModalTwo">open modal two</button>
<!-- <input type = "text" ref="name">
<button @click = "handleClick">click me</button> -->
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
  data() {
    return {
      title: 'My First Vue App :)',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    },
  //   handleClick(){
  //     console.log(this.$refs.name)
  //     this.$refs.name.classList.add("active")
  //     this.$refs.name.focus()
  //   }
  }

}
</script>

<style>
#app, .modals{
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
</style>
