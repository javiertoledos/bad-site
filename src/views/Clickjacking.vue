<template>
  <div class="clickjacking">
    <h1 class="title is-1">Clickjacking example</h1>
    <div class="mask">
      <button class="button">Win something!</button>
      <iframe src="https://web-security-demo.web.app" height="1000" width="400" />
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
.mask { 
  overflow: hidden;
  height: 50px;
  width: 200px;
  z-index:0;
  left: auto;
  right: auto;
  margin: auto;
  position: relative;
}
.mask button {
  position: absolute;
  top: 0;
  left: 0;
}
.mask iframe {
  position: absolute;
  top: -360px;
  left: -190px;
  opacity: 0;
}
</style>