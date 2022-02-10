<template>
  <div style="width:100%;position:relative">
    <div
      v-if="clicked"
      style="position:absolute;z-index:1000;width:100%"
      class="text-center"
      @click="clicked = false"
    >
      <i class="fa fa-times-circle mt-2" style="color:white;cursor:pointer"></i>
    </div>
    <div
      v-if="!clicked"
      class="d-flex justify-content-center align-items-center title-card"
      @click="clicked = true"
    >
      <div style="text-align:center;padding:10px;color:white">{{element}}</div>
    </div>
    <div
      class="card"
      :style="clicked ? {  'color': 'rgb(88 199 250 / 100%)' , 'transition': 'color 1s'} : '' "
    >Magic Card</div>
    <div  style="background:yellow;margin-left:25%;width:50%;text-align:center;
    border-bottom-left-radius:8px;
    border-bottom-right-radius:8px;
    margin-top:5px
    ">
      <div>2 Days left</div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["element"],
  data() {
    return {
      clicked: false
    };
  }
};
</script>
<style scoped>
@property --rotate {
  syntax: "<angle>";
  initial-value: 132deg;
  inherits: false;
}

:root {
  --card-height: 65vh;
  --card-width: calc(var(--card-height) / 1.5);
}

body {
  min-height: 100vh;
  background: #212534;
  display: flex;
  align-items: center;
  flex-direction: column;
  padding-top: 2rem;
  padding-bottom: 2rem;
  box-sizing: border-box;
}
.title-card {
  font-family: cursive;
  font-size: 1.5em;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1000;
  width: 100%;
  height: 200px;
}
.card {
  /* background: #191c29; */
  background: #0b2031;
  width: 100%;
  height: 200px;
  padding: 3px;
  position: relative;
  border-radius: 6px;
  justify-content: center;
  align-items: center;
  text-align: center;
  display: flex;
  font-size: 1.5em;
  color: rgb(88 199 250 / 0%);
  cursor: pointer;
  font-family: cursive;
}

/* .card:hover:before,
.card:hover:after {
  animation: none;
  opacity: 0;
} */

.card::before {
  content: "";
  width: 104%;
  height: 102%;
  border-radius: 8px;
  background-image: linear-gradient(
    var(--rotate),
    #5ddcff,
    #3c67e3 43%,
    #4e00c2
  );
  position: absolute;
  z-index: -1;
  top: -1%;
  left: -2%;
  animation: spin 2.5s linear infinite;
}

.card::after {
  position: absolute;
  content: "";
  top: calc(var(--card-height) / 6);
  left: 0;
  right: 0;
  z-index: -1;
  height: 100%;
  width: 100%;
  margin: 0 auto;
  transform: scale(0.8);
  filter: blur(calc(var(--card-height) / 6));
  background-image: linear-gradient(
    var(--rotate),
    #5ddcff,
    #3c67e3 43%,
    #4e00c2
  );
  opacity: 1;
  transition: opacity 0.5s;
  animation: spin 2.5s linear infinite;
}

@keyframes spin {
  0% {
    --rotate: 0deg;
  }
  100% {
    --rotate: 360deg;
  }
}

a {
  color: #212534;
  text-decoration: none;
  font-family: sans-serif;
  font-weight: bold;
  margin-top: 2rem;
}
</style>