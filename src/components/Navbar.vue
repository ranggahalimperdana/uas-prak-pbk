<template>
  <nav class="navbar">
    <div class="navbar-brand">
      <router-link to="/" class="navbar-item">UAS Praktikum PBK - Projek API Cuaca</router-link>
    </div>
    <div class="hamburger" @click="toggleDropdown">
      <div class="bar" :class="{ 'bar1': isDropdownActive }"></div>
      <div class="bar" :class="{ 'bar2': isDropdownActive }"></div>
      <div class="bar" :class="{ 'bar3': isDropdownActive }"></div>
    </div>
    <div class="dropdown-menu" :class="{ 'is-active': isDropdownActive }">
      <a href="https://rangga-project-cv.web.app/" class="navbar-item" target="_blank">TUGAS 1</a>
      <a href="https://rangga-23548.web.app/" class="navbar-item" target="_blank">TUGAS 2</a>
      <a href="https://tugas3-pbk.web.app/" class="navbar-item" target="_blank">TUGAS 3</a>
      <a href="https://tugas4pbk-rangga.web.app/" class="navbar-item" target="_blank">TUGAS 4</a>
      <a href="https://landingpagevue.vercel.app/" class="navbar-item" target="_blank">TUGAS 5</a>
      <a href="https://tugas6pbk.vercel.app/" class="navbar-item" target="_blank">TUGAS 6</a>
      <a href="https://tugas7pbk-rangga.web.app/" class="navbar-item" target="_blank">TUGAS 7</a>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isDropdownActive: false
    };
  },
  methods: {
    toggleDropdown() {
      this.isDropdownActive = !this.isDropdownActive;
    }
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap'); /* Mengimpor font Poppins */

.navbar {
  background-color: salmon; /* Menggunakan warna salmon untuk background */
  color: #fff;
  padding: 10px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Poppins', sans-serif; /* Mengatur font Poppins */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); /* Bayangan halus */
  position: relative; /* Menyesuaikan posisi relatif untuk menu dropdown */
}

.navbar-brand {
  display: flex;
  align-items: center;
}

.navbar-item {
  color: #fff;
  text-decoration: none;
  margin: 0 10px;
  padding: 10px;
  border-radius: 5px;
  transition: background-color 0.3s, color 0.3s, transform 0.3s; /* Animasi transisi */
  font-size: 18px; /* Menambah ukuran font */
}

.navbar-item:hover {
  background-color: rgba(255, 255, 255, 0.2); /* Mengubah background saat hover */
  transform: scale(1.05); /* Efek scale saat hover */
}

.hamburger {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  height: 25px;
  cursor: pointer; /* Menambahkan cursor pointer untuk menunjukkan klik-able */
}

.bar {
  width: 25px;
  height: 3px;
  background-color: #fff;
  transition: transform 0.3s, opacity 0.3s; /* Animasi transisi */
}

.bar1 {
  transform: rotate(45deg) translate(5px, 5px);
}

.bar2 {
  opacity: 0;
}

.bar3 {
  transform: rotate(-45deg) translate(5px, -5px);
}

.dropdown-menu {
  display: none;
  position: absolute;
  top: calc(100% + 10px); /* Menyesuaikan jarak dari navbar */
  right: 20px;
  background-color: rgba(27, 30, 29, 0.9); /* Background dengan transparansi */
  border-radius: 10px;
  padding: 10px 0; /* Mengurangi padding untuk konten lebih ringan */
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2); /* Bayangan halus */
  z-index: 1000;
  width: 200px;
  opacity: 0; /* Mengatur opacity untuk animasi */
  pointer-events: none; /* Menonaktifkan event di luar tampilan */
  transition: opacity 0.3s ease, transform 0.3s ease; /* Animasi opacity dan transform */
}

.dropdown-menu.is-active {
  display: block;
  opacity: 1; /* Menampilkan dropdown */
  pointer-events: auto; /* Mengaktifkan event kembali */
  transform: translateY(0); /* Mengatur transform */
}

.dropdown-menu .navbar-item {
  display: block;
  width: 100%;
  padding: 10px 20px; /* Menyesuaikan padding untuk konten */
  font-size: 16px; /* Menurunkan ukuran font untuk konten dropdown */
}

.dropdown-menu .navbar-item:hover {
  background-color: rgba(255, 255, 255, 0.2); /* Mengubah background saat hover */
}

.navbar-item.active {
  background-color: rgba(255, 255, 255, 0.2); /* Background untuk item aktif */
}
</style>
