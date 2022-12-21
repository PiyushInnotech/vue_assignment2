
<template>
  <div class="assign">
    <div class="focusBtn">
      <input type="text" ref="inputRef" />
      <button @click="mounted">Focus</button>
      <button @click="this.showModel=true">Show Modal</button>
    </div>
      <Modal
        title="Signup for the Giveaway"
        content="Grap your item for half prize"
        theme="sales"
        class="modal"
        v-show="showModel"
        @close="this.showModel=false"
        @open="this.showModel=true"
      >
      </Modal>
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  data() {
    return {
      showModel: false
    }
  },
  methods: {
    mounted() {
      this.$refs.inputRef.focus();
    },
  },
  components: {
    Modal,
  },
};
</script>


<style>
.assign {
  position: relative;
  width: 100%;
}
.focusBtn {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.focusBtn input {
  width: 200px;
  height: 25px;
}
.focusBtn button {
  width: 150px;
  height: 30px;
  font-size: 20px;
  margin-top: 10px;
}
.modal {
  position: absolute;
  top: 0;
}
</style>
