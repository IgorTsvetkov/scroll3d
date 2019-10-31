<template>
  <div
    class="scroll360"
    @mousemove="changePosition"
    @mousedown="active=true"
    @mouseup="active=false"
    @mouseleave="active=false"
  >
    <img draggable="false" :src="images[this.indexActive].data.attrs.src" />
  </div>
</template>

<script>
export default {
  name: "scroll360",
  props: {
    step: {
      type: Number,
      default: 10
    }
  },
  data() {
    return {
      images: [],
      currentPositionX:undefined,
      indexActive: 0,
      active: false,
      length: undefined,
      lastIndex:undefined,
    };
  },
  methods: {
    changePosition: function(e) {
      let positionX=e.clientX;
      if (this.active) {
        let deltaX=positionX - this.currentPositionX;
        if (deltaX >= this.step) {  
              this.currentPositionX= positionX;   
              this.indexActive+=Math.floor(deltaX/this.step); 
              if (this.indexActive > this.lastIndex) 
                this.indexActive-=this.length;
        }
        if(-deltaX >= this.step)
        {
              this.currentPositionX= positionX;   
              this.indexActive+=Math.ceil(deltaX/this.step); 
              if (this.indexActive < 0) 
                this.indexActive+=this.length;
        }
        return;
      }
      this.currentPositionX = positionX;
    },
  },
  created: function() {
    this.images = this.$slots.default.filter(el => el.tag == "img");
    this.length = this.images.length;
    this.lastIndex = this.images.length-1;
  }
};
</script>
<style scoped>
</style>
