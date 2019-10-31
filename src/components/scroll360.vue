<template>
  <div class="scroll360"
   @mousemove="changePosition"
    @mousedown="active=true" @mouseup="active=false" @mouseleave="active=false"> 
    <img draggable="false" :src="images[this.indexActive].data.attrs.src">
  </div>
</template>

<script>
export default {
  name: "scroll360",
  props: {
    step: {
      type: Number,
      default: 10
    },
  },
  data() {
    return {
      images: [],
      currentPosition:{x:undefined,y:undefined},
      indexActive:0,
      active:false,
      length:undefined,
    };
  },
  methods: {
    changePosition:function(e){
      let position={
        x:e.clientX,
      };  
      if(this.active){
        if((position.x-this.currentPosition.x)>this.step){
          if(this.indexActive<this.length-1)
            this.indexActive++;            
          else
            this.indexActive=0;
          this.currentPosition.x=position.x;
        }
        else if(-(position.x-this.currentPosition.x)>this.step){
          if(this.indexActive>0)
            this.indexActive--;              
          else
            this.indexActive=this.length-1;        
          this.currentPosition.x=position.x;
        }
        return;
      }
      this.currentPosition=position;
    },
  },
  created: function() {
    this.images=this.$slots.default.filter(el => el.tag == "img");
    this.length=this.images.length;
  }
};
</script>
<style scoped>
</style>
