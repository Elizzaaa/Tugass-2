<template>
  <div>
    <h1>{{ pageTitle }}</h1>
    <p :class="{ 'highlight': isHighlighted }">Ini adalah contoh halaman web dengan beberapa elemen HTML.</p>
    <input type="text" v-model="inputText" @input="updateText">
    <p :style="{ color: textColor }">Teks yang dimasukkan: {{ inputText }}</p>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const pageTitle = ref('Halaman Web dengan Vue.js');
    const isHighlighted = ref(false);
    const inputText = ref('');
    const textColor = ref('black');

    const updateText = (event) => {
      inputText.value = event.target.value;
      if (inputText.value.length > 10) {
        isHighlighted.value = true;
        textColor.value = 'red';
      } else {
        isHighlighted.value = false;
        textColor.value = 'black';
      }
    };

    return {
      pageTitle,
      isHighlighted,
      inputText,
      textColor,
      updateText
    };
  }
};
</script>

<style scoped>
.highlight {
  color: blue;
  font-weight: bold;
}
</style>
