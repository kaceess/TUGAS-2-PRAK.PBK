<template>
  <div id="app"> <!-- Kontainer utama untuk Vue.js -->
    <h1>Tugas 2</h1> <!-- Heading utama -->

    <!-- Input teks dengan v-model untuk mengikat data -->
    <input type="text" v-model="userInput" placeholder="Masukkan teks di sini">

    <!-- Paragraf dengan class dan style bindings -->
    <p :class="{ highlighted: isHighlighted }" :style="{ color: textColor }">
      Teks ini dapat berubah berdasarkan input Anda: {{ userInput }}
    </p>

    <!-- Tombol untuk mengubah highlight dan warna teks -->
    <button @click="toggleHighlight">Ubah Latar Teks</button>
    <button @click="changeTextColor">Ubah Warna Teks</button>
  </div>
</template>

<script>
export default {
  data() { // Data Vue untuk aplikasi
    return {
      userInput: '', // Data yang terikat dengan input teks
      isHighlighted: false, // Status untuk highlight
      textColor: 'black' // Warna teks
    };
  },
  methods: {
    toggleHighlight() { // Metode untuk toggle highlight
      this.isHighlighted = !this.isHighlighted;
    },
    changeTextColor() { // Metode untuk mengubah warna teks
      this.textColor = this.textColor === 'black' ? 'white' : 'black';
    }
  }
};
</script>

<style scoped>
/* Gaya untuk komponen Vue ini */
#app {
  text-align: center; /* Penataan teks */
}

.highlighted { /* Gaya untuk elemen yang di-highlight */
  background-color: pink; /* Warna latar kuning */
  font-weight: bold; /* Tebal */
}

button {
  margin: 10px; /* Margin untuk tombol */
}

p {
  color: white; /* Warna dasar teks */
}
</style>