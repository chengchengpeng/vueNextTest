<template>
  <div class="hello">
    <input
      ref="fileInput"
      type="file"
      :style="{display: 'none'}"
      @change="handleFileChange"
    >
    <button @click="handelClick">点击1</button>
    <slot name="header" total="1" message="cccc">
     
    </slot>
    <slot>
      
    </slot>
  </div>
</template>

<script>
import { defineComponent,ref } from "vue";
export default defineComponent({
  props:{
    nums:{
      type:Number,
    }
  },
  data(){
    return {
      key:10
    }
  },
  setup() {
    const fileInput = ref(null);
    const setupValue = ref(20);
    const handleFileChange = (e) =>{
      const files = e.target.files[0]
      const url = URL.createObjectURL(files)
      console.log(url,files);
      // const fileReader = new FileReader()
      //   fileReader.readAsDataURL(files)
      //   fileReader.addEventListener('load', () => {
      //     console.log(fileReader.result);
      //   })
       var formData = new FormData()

      formData.append(files.name, files)
      console.log(formData);
    }
    const handelClick = () =>{
      fileInput.value.click()
    }
    return {
      fileInput,
      handleFileChange,
      handelClick,
      setupValue
    }
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
