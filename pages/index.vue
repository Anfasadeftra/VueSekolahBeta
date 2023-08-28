<template>
  <div class="container">
    <h1>Halo Selamat Datang</h1>
    <img :src="imagePath" alt="Gambar" width="650px" class="gambar">
  </div>
</template>

<script>
import MyImage from '@/Img/skill.jpg';

export default {
  data() {
    return {
      imagePath: MyImage
    };
  }
}
</script>

<style scoped>
.container{
  width: 75%;
  margin: 100x auto;
  text-align: center;
}

.menu{
  list-style: none;
  margin-bottom: 20px;
}

.menu li {
  display: inline;
}

.menu li a {
  padding:  20px;
  text-decoration: none;
}

.gambar {
  margin-bottom: 50px;
}
</style>
