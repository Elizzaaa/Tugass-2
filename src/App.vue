<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TUGAS PERTEMUAN 2</title>
  <!-- Tambahkan CDN Vue.js -->
  <script src="https://cdn.jsdelivr.net/npm/vue@2"></script>
  <style>
    .highlight {
      color: blue;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div id="app">
    <h1>{{ pageTitle }}</h1>
    <p v-bind:class="{ 'highlight': isHighlighted }">Ini adalah contoh halaman web dengan beberapa elemen HTML.</p>
    <input type="text" v-model="inputText" @input="updateText">
    <p v-bind:style="{ color: textColor }">Teks yang dimasukkan: {{ inputText }}</p>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        pageTitle: 'Halaman Web dengan Vue.js',
        isHighlighted: false,
        inputText: '',
        textColor: 'black'
      },
      methods: {
        updateText: function(event) {
          this.inputText = event.target.value;
          if (this.inputText.length > 10) {
            this.isHighlighted = true;
            this.textColor = 'red';
          } else {
            this.isHighlighted = false;
            this.textColor = 'black';
          }
        },
        header-text h1{
          font-size: 20%;
        }
      }
    });
  </script>
</body>
</html>
