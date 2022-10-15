<template>
  <h1>{{ title }}</h1>
  <br />
  <!-- <input type="text" ref="name" /> -->
  <!-- <button @click="handleClick">click me</button> -->
  <button @click="toggleModal">open modal</button>
  <button @click="toggleModal2">open modal 2</button>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>Daftar Sekarang Juga!</h1>
      <p>Coming Up Next the bonus!</p>
    </Modal>
  </teleport>
  <teleport to=".modals" v-if="showModal2">
    <Modal theme="blk" @close="toggleModal2">
      <template v-slot:links>
        <a href="#">Get Black Friday</a>
        <a href="#">No Ingfo</a>
      </template>
      <h1>Black Fiday Is Coming</h1>
      <p>Coming Up October 30th</p>
    </Modal>
  </teleport>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal, Modal },
  data() {
    return {
      title: "My First LuVue App :)",
      showModal: false,
      showModal2:false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2;
    },
  },
};
</script>

<style>

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
