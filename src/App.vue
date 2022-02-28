<template>
  <div v-if="showModal">
      <h1>{{ title }}</h1>
  <!-- <input type="text" ref="name"> -->
  <!-- <button @click="handleClick">CLick Me</button> -->
     <!-- <Modal :header="header" :text="text" theme="sale"
     @close="toggleModal"/>    -->
     <modal theme="sale" @close="toggleModal">
        <template v-slot:links>
           <a href="#">Sign up now</a>
           <a href="#">more info here please</a>
        </template>
        <h1>Welcome to FlexiconTech</h1>
        <p>You will be very much excited learning here!</p>
     </modal>
  </div>
  <button @click="toggleModal">open modal</button>
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  components: { Modal },
  name: 'App',
 data(){
   return{
     title:'My new vue tutorial',
     header:'Sign up for the giveaway',
     text:'Grab your Buhari new bag at the cheapest price!',
     showModal: false
   }
 },
 methods:{
   handleClick(){
     console.log(this.$refs.name)
     this.$refs.name.classList.add('active')
     this.$refs.name.focus()

   },
   toggleModal(){
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
p, h1{
  margin-top: 23px;
  color: white;
}
</style>
