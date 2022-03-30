<template>
  <div>
    <CalcModel></CalcModel>
  </div>
</template>


<script>
import CalcModel from "./components/CalcModel.vue";

export default {
  components: { CalcModel },
};
</script>


<style>
* {
  transition: all 0.3s;
  font-weight: 600;
}

body {
  display: flex;
  justify-content: center;
  
}

#app {
  width: 400px;
  box-shadow: 0 3px 15px gray;
}
.grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  width: 100%;
}
</style>
