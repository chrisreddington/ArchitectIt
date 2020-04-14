<template>
  <div width="100%" height="100%">
    <canvas
      background="#000000"
      v-bind:width="this.$parent.width"
      v-bind:height="this.$parent.height"
      id="DropArea"
      v-on:drop="drop"
      v-on:dragover="allowDrop"
    />
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      msg: "Hello World! This is a Event listener test.",
      windowWidth: 0,
      windowHeight: 0
    };
  },
  methods: {
    elementScale: function(element){
        return element.offsetWidth === 0 ? 0 : (element.width / element.offsetWidth);
    },
    allowDrop: function(event) {
      event.preventDefault();
    },
    drop: function(event) {    
    var canvas = document.getElementById("DropArea");
    var ctx = canvas.getContext("2d");     
    var img = document.getElementById("1");
    var scale = this.elementScale(canvas);
    var currentPoint = {x: event.clientX * scale, y: event.clientY * scale};
    ctx.drawImage(img, event.clientX-100, event.clientY-100); // On hover nothing will show 

      console.log(event);
      console.log(ctx);
    }
  },
  mounted() {}
};
</script>

<style lang="scss">
canvas {
  background: black;
  box-shadow: 0px 2px 3px rgba(0, 0, 0, 0.2);
}
</style>
