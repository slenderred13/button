<template>
  <div id="example-1">
    <!--<button @click="upFunction()" class="btn btn-info">{{label}}</button>-->
    <p v-bind:style="{fontSize: fsize + 'px' }"> All Score : {{ counter }} </p>
    <button @click="LikeFunction()" class="btn btn-primary">
      <i class='far fa-thumbs-up' style='color:white' ></i>
    </button>
    <button @click="LoveFunction()" class="btn btn-danger">
      <i class='far fa-heart' style='color:white' ></i>
      </button>
    <button @click="HahaFunction()" class="btn btn-warning">
      <i class='far fa-grin-squint-tears' style='color:black'></i>
    </button>
    <button @click="WowFunction()" class="btn btn-success">
      <i class='far fa-dizzy' style='color:black' ></i>
      </button>
    <button @click="SadFunction()" class="btn btn-info">
      <i class='far fa-sad-tear' style='color:black' ></i>
      </button>
    <button @click="AngryFunction()" class="btn btn-danger">
      <i class='far fa-grimace' style='color:black' ></i>
      </button>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      counter: 0,
    }
  },
  methods:{
    LikeFunction: function(){
      this.counter += 1
      //1.ส่งค่าตัวแปร counter ออกไปโดยผ่านตัวแปร cc
      this.$emit('cc',this.counter)

    },
    LoveFunction: function(){
      this.counter += 10
      this.$emit("cc", this.counter);
    },
    HahaFunction: function(){
      this.counter += 5
      this.$emit("cc", this.counter);
    },
    WowFunction: function(){
      this.counter += 20
      this.$emit("cc", this.counter);
    },
    SadFunction: function(){
      this.counter -= 5
      this.$emit("cc", this.counter);
    },
    AngryFunction: function(){
      this.counter -= 50
      this.$emit("cc", this.counter);
    },
    ResetFunction: function () {
      this.counter = 0;
      this.$emit("cc", this.counter);
    },
    sum(counterValue){
      this.total += counterValue
    },
  },
  props: {
    label: String
  },
};
</script>

<style>
</style>

