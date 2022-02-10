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
    <div class="d-flex justify-content-center">
      <div class="container d-flex ">
        <client-only>
          <draggable class="d-flex justify-content-center row text-dark" style v-model="myArray">
            <div v-for="element in myArray" :key="element">
              <div class="m-3" style="min-height:100px">
                <Card style="min-width:100%;width:20vw"></Card>
              </div>
            </div>
          </draggable>
        </client-only>
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from "../components/Sidebar.vue";
import Card from "../components/Card.vue";
export default {
  data() {
    return {
      myArray: ["1", "2", "3", "4" , '5' , '6' , '7', '8' ]
    };
  },
  components: {
    Card,
    Sidebar
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