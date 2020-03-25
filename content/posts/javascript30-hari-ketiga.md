+++
categories = ["Pemrograman"]
date = 2020-03-25T09:00:00Z
tags = ["javascript"]
title = "JavaScript30: Hari Ketiga"

+++
Pembahasan di hari ini adalah CSS variabel. Jadi, sebenernya CSS itu punya variabel, yang mana sangat memudahkan kita untuk mengganti nilai dari suatu properti, sama seperti variabel pada umumnya.

Dengan bantuan javascript, kita bisa mengganti variabel tersebut. Sehingga tidak perlu merubah satu per satu properti pada masing-masing selektor. Karena nilai dari properti itu sudah diatur oleh CSS variabelnya.

Contoh penggunaan yang dipraktekkan pada kali ini yaitu mengatur padding, blur, dan warna pada halaman web. Dengan memanfaatkan HTML `input` yang tipenya adalah `range` untuk mengatur ukuran padding dan blur, dan tipe `color` untuk mengatur warnanya.

Berikut kodingan yang udah jadi.

    const inputs = document.querySelectorAll('.controls input');
    
    function handleUpdate() {
      const suffix = this.dataset.sizing || '';
      document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
    }
    
    inputs.forEach(input => input.addEventListener('change', handleUpdate));
    inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));

**Algoritma**

Pada template yang telah disediakan, elemen `form` memiliki kelas `control`, sehingga kita membuat variabel baru untuk mengambil setiap elemen `input`. `document.querySelectorAll()` akan mengembalikan sebuah _NodeList,_ untuk mengetahui elemen mana yang berubah, digunakan method `addEventListener()` yang dimasukkan pada method `forEach`. 

Parameter tipe yang digunakan untuk method `addEventListener` ada dua, `change` untuk mengetahui nilai setelah berubah, `mousemove` untuk mengetahui secara langsung nilai yang berubah ketika input range digeser.

Parameter _listener_ diisi dengan fungsi `handleUpdate`, yang bekerja untuk mengganti nilai properti variabel CSS yang telah dibuat.

Dari beberapa video JavaScript yang udah aku tonton, cara terbaik untuk mengetahui apa itu `this` (kalo belum tau), atau parameter yang ada pada _built-in function_ yaitu dengan `console.log` parameter tersebut.

Juga untuk mengetahui objek apa yang dimiliki sebuah elemen, bisa dilihat di console pada browser. Sekian yang bisa dibagi kali ini, kalo bingung bisa cari di google penjelasan lengkapnya, karena ini hanya sebuah catatan biar makin paham cara kerja sebuah kodingan.

Terimakasih.

Referensi: 

Seperti biasa, [Mozilla Developer Network](https://developer.mozilla.org/en-US/ "Dokumentasi")