<template>
  <div>
    
    <h1>{{ greeting }}</h1>
    <a href=""><img src="/src/assets/WhatsApp Image 2024-05-07 at 01.22.04.jpeg" alt="" width="200px" height="200px"style="border-radius: 10%;" ></a>
    <p>masukkan paling tidak 20 huruf untuk merubah warna</p>
    <!-- Input teks dengan binding -->
    <input type="text" v-model="inputText" @input="handleInput" />
    <!-- Elemen dengan class binding dan style binding -->
    <p :class="{ important: isImportant }" :style="{ color: textColor }">
      {{ dynamicText }}
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      greeting: 'Selamat Datang di web saya!',
      inputText: '',
      dynamicText: 'Teks Dinamis',
      isImportant: false,
      textColor: 'white'
    };
  },
  methods: {
    handleInput(event) {
      this.dynamicText = event.target.value;
      this.isImportant = event.target.value.length > 20;
      this.textColor = this.isImportant ? 'skyblue' : 'white';
    }
  }
};
</script>

<style>
.important {
  font-weight: bold;
}
</style>
