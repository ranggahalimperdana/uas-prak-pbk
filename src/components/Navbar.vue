<template>
  <nav class="navbar">
    <div class="navbar-brand">
      <router-link to="/" class="navbar-item">WEATHER</router-link>
    </div>
    <div class="task-links">
      <div class="dropdown" @click="toggleDropdown">
        <div class="navbar-item">Tugas Arfan Hasanah ▼</div> <!-- Menambah panah ke bawah -->
        <div class="dropdown-menu" :class="{ 'is-active': isDropdownActive }">
          <a href="https://arfan-portofolio-cv.web.app/" class="navbar-item" target="_blank">TUGAS 1</a>
          <a href="https://arfan-hasanah-project.web.app/" class="navbar-item" target="_blank">TUGAS 2</a>
          <a href="https://arfan-hasanah-tugas3pbk.web.app/" class="navbar-item" target="_blank">TUGAS 3</a>
          <a href="https://tugas4-pbk-omega.vercel.app/" class="navbar-item" target="_blank">TUGAS 4</a>
          <a href="https://tugas5-pbk.vercel.app/" class="navbar-item" target="_blank">TUGAS 5</a>
          <a href="https://tugas6-pbk.vercel.app/" class="navbar-item" target="_blank">TUGAS 6</a>
          <a href="https://tugas7-pbk-sage.vercel.app/" class="navbar-item" target="_blank">TUGAS 7</a>
        </div>
      </div>
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
  background-color: #57a4f1d4;
  color: #fff;
  padding: 10px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: 'Poppins', sans-serif; /* Mengatur font Poppins */
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
  transition: background-color 0.3s, color 0.3s;
  font-size: 18px; /* Menambah ukuran font */
}

.navbar-item:hover {
  background-color: #abbed1;
}

.task-links {
  display: flex;
  align-items: center;
}

.dropdown {
  position: relative;
  cursor: pointer; /* Menambahkan cursor pointer untuk menunjukkan klik-able */
}

.dropdown-menu {
  display: none;
  position: absolute;
  top: calc(100% + 10px); /* Menyesuaikan jarak dari navbar */
  left: 50%;
  transform: translateX(-50%);
  background-color: #1b1e1d;
  border-radius: 10px;
  padding: 10px 0; /* Mengurangi padding untuk konten lebih ringan */
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  width: 200px;
  opacity: 0; /* Mengatur opacity untuk animasi */
  pointer-events: none; /* Menonaktifkan event di luar tampilan */
  transition: opacity 0.3s ease; /* Animasi opacity */
}

.dropdown-menu.is-active {
  display: block;
  opacity: 1; /* Menampilkan dropdown */
  pointer-events: auto; /* Mengaktifkan event kembali */
}

.dropdown-menu .navbar-item {
  display: block;
  width: 100%;
  padding: 10px 20px; /* Menyesuaikan padding untuk konten */
  font-size: 16px; /* Menurunkan ukuran font untuk konten dropdown */
}

.dropdown-menu .navbar-item:hover {
  background-color: #abbed1;
}

.navbar-item.active {
  background-color: #abbed1;
}
</style>
