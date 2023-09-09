<template>
  <div>
    <footer>
      <div class="container text-center py-3">
        &copy; 2023 Sewakuu
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "Alkademi",
    };
  },
};
</script>

<style scoped>
html, body {
  height: 100%;
  margin: 0;
  padding: 0;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

footer {
  margin-top: auto;
  background-color: #1c1d1f;
  color: #ffffff;
}
</style>