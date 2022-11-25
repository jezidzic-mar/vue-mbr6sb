<template>
  <div>
     <input type="text" v-model="qrtext"></input>
     <input type="text" v-model="color"></input>
     <div :style="{background: color}">
      <ColorPicker
        theme="light"
        :color="color"
        :sucker-hide="false"
        :sucker-canvas="suckerCanvas"
        :sucker-area="suckerArea"
        @changeColor="changeColor"
        @openSucker="openSucker"
      />
    </div>
  </div>
</template>

<script>

import { ColorPicker } from 'vue-color-kit';
import 'vue-color-kit/dist/vue-color-kit.css';
import { ref } from 'vue';

export default {
  name: "Main" ,
    components:{
      ColorPicker,
    }, 
    setup(){
      let qrtext;
      let color = ref('#FF007B');
      let suckerHide = ref(false);
      let suckerCanvas = null;
      let suckerArea = ref([]);
      let showcolorpicker = ref(true);
      function changeColor(_color) {
        //const { r, g, b, a } = _color.rgba;
        //color.value = `rgba(${r}, ${g}, ${b}, ${a})`;
        color.value = _color.hex;
      }
      function changeColor(_color) {
        //const { r, g, b, a } = _color.rgba;
        //color.value = `rgba(${r}, ${g}, ${b}, ${a})`;
        color.value = _color.hex;
      }
      function openSucker(isOpen) {
        if (isOpen) {
          // ... canvas be created
          // this.suckerCanvas = canvas
          // this.suckerArea = [x1, y1, x2, y2]
        } else {
          // this.suckerCanvas && this.suckerCanvas.remove
        }
      }
      return {
        color,
        suckerHide,
        suckerCanvas,
        suckerArea,
        changeColor,
        showcolorpicker,
        openSucker,
      };
  }
}
</script>

<style scoped>
  .input{
    display: flex;
    flex-direction:column;
  }
</style>