<template>
  <div class="box" @click.prevent.capture="$emit('close')">
    <div
      :class="theme === 'sale' ? 'red' : 'boxWrap'"
      @click.prevent="$emit('open')"
    >
      <h1 class="boxTitle">{{ title }}</h1>
      <h3 class="boxContent">{{ content }}</h3>
      <slot></slot>
      <div class="links">
        <slot name="link"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {
      title: "",
      content: "",
      theme: "",
    };
  },
  props: ["title", "content", "theme"],
  emits: ["close", "open"],
  methods: {},
};
</script>

<style scoped>
#Modal {
  width: 100%;
  height: 100vh;
}
.box {
  width: 100%;
  height: 100vh;
  background-color: grey;
  position: relative;
  margin: 0;
}
.red {
  width: 500px;
  height: 250px;
  border-radius: 25px;
  position: absolute;
  background-color: red;
  top: 20%;
  text-align: center;
  color: white;
  left: 35%;
}
.boxWrap {
  width: 500px;
  height: 350px;
  border-radius: 25px;
  position: absolute;
  background-color: white;
  top: 20%;
  text-align: center;
  color: green;
  left: 35%;
}
.boxTitle {
  margin-top: 10%;
  font-size: 40px;
}
.boxContent {
  margin-top: 10%;
  font-size: 25px;
}
.links {
  font-size: 20px;
  background-color: lightskyblue;
  width: 150px;
  margin-left: 35%;
  height: 35px;
  border: solid 2px black;
  border-radius: 30px;
  padding: 8px;
}
</style>
