<template>
  <div>
    <Sidebar></Sidebar>
    <h1>Color mode: {{ $colorMode.value }}</h1>
    <select v-model="$colorMode.preference">
      <option value="system">System</option>
      <option value="light">Light</option>
      <option value="dark">Dark</option>
      <option value="sepia">Sepia</option>
    </select>
    <div>
      <div class="d-flex justify-content-around">
        <draggable class="row text-dark" style v-model="myArray">
          <div v-for="element in myArray" :key="element">
            <div class="bg-success col-3 p-5 m-2">{{element}}</div>
          </div>
        </draggable>
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from '../components/Sidebar.vue'
export default {
  data() {
    return {
      myArray: ["1", "2", "3", "4"]
    };
  },
  components:{
    Sidebar:Sidebar
  }
};
</script>
<style>
body {
  background-color: #fff;
  color: rgba(0, 0, 0, 0.8);
}
.dark-mode body {
  background-color: #091a28;
  color: #ebf4f1;
}
.sepia-mode body {
  background-color: #f1e7d0;
  color: #433422;
}
</style>