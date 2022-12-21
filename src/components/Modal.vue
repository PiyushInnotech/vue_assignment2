<template>
  <div class="box" @click="$emit('close')" >
    <div :class="theme==='sale' ? 'red' : 'box1'" 
          @click.prevent="$emit('open')">
        <h1 class="boxTitle">{{title}}</h1>
        <h3 class="boxContent">{{content}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {
      title:"",
      content:"",
      theme:'',
    };
  },
  props:['title','content','theme', ],
  emits:['close','open'],
  methods: {
  },
};
</script>

<style>
#Modal{
    width: 100%;
    height: 100vh;
}
.box{
    width: 100%;
    height: 100vh;
    background-color: grey;
    position: relative;
    margin: 0;
}
.red{
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
.box1{
    width: 500px;
    height: 250px;
    border-radius: 25px;
    position: absolute;
    background-color: white;
    top: 20%;
    text-align: center;
    color: green;
    left: 35%;
}
.boxTitle{
    margin-top: 10%;
    font-size: 40px;
}
.boxContent{
    margin-top: 10%;
    font-size: 25px;
}

</style>
