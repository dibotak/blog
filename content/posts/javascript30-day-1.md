+++
categories = "Pemrograman"
date = 2020-03-21T17:02:00Z
tags = ["javascript"]
title = "JavaScript 30: Perkenalan dan Hari Pertama."

+++
Di waktu seperti ini, rasa bosan datang dan ingin sekali rasanya mencoba hal baru. Lagi-lagi seperti siklus yang sudah sudah. <!--more-->Padahal JavaScript saja belum sepenuhnya paham, buat programnya saja belum. Bosan dengan latihan logika, ingin sekali membuat sesuatu.

Berusaha untuk tetap bertahan belajar JavaScript, jadinya ya mencoba hal baru. Tetap belajar. Artikel ini berisi tentang catatan teknis supaya mengerti bagaimana kode itu bisa bekerja.

Akhirnya aku memutuskan untuk mencoba lagi mengikuti program JavaScript30 yang dibuat oleh WesBos. Setelah sebelumnya tidak bisa mengakses videonya karena di web tersebut videonya di host di vimeo, yang mana sama sekali gak bisa dibuka. Pertama kali tahu web itu dari [artikel ini](https://medium.com/javascript-indonesia-community/referensi-belajar-pengembangan-app-dengan-javascript-2b0c071d3262 "Referensi Belajar Pengembangan Aplikasi JavaScript"), sama sekali belum pernah mencobanya. Kemudian mendengarkan podcast dari [dekadensiotak](https://open.spotify.com/show/7CXYFUB7c8vx1OqYCSihaC "Podcast Dekadensiotak"), membuat penasaran dan ingin mencobanya.

Dicarilah ke youtube, ternyata ada channel si pembuat dan juga ada playlistnya. Ya sudah, jadinya mulai ikut.

Baik, hari pertama itu aku belajar membuat drum kit. Ketika menekan salah satu tombol di keyboard, akan memainkan audio dan mengubah tampilan html sementara.

Berikut kode yang sudah jadi:

    function playSound(e) {
        const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
        const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
        if (!audio) return; // stop the function from running all together
        audio.currentTime = 0;
        audio.play();
        key.classList.add('playing');
      }
      
      function removeTransition(e) {
        if (e.propertyName !== 'transform') return; // skip it if it's not a transform
        this.classList.remove('playing');
      }
    
      const keys = document.querySelectorAll('.key');
      keys.forEach(key => key.addEventListener('transitionend', removeTransition))
    
      window.addEventListener('keydown', playSound);

Algoritma untuk membuat drum kit ini adalah, kita ingin halaman web mengetahui tombol keyboard apa yang kita tekan, setelah itu halaman akan mencocokkan, apakah tombol tersebut termasuk dalam drum kit yang telah kita buat. Jika iya, maka javascript akan menambahkan kelas pada elemen html sesaat (untuk mengubah tampilan pada web), dan memainkan audio. kelas yang ditambahkan sesaat itu akan hilang sesuai dengan transisi yang telah diset pada css.

Agar web mengetahui apa yang kita tekan pada keyboard, kita menggunakan method `addEventListener()` pada `EventTarget`. Yang mana targetnya adalah `window`. Parameter yang akan digunakan pada method tersebut adalah `type` dan `listener`. `type` merupakan tipe dari event yang akan kita gunakan, pada kasus ini kita menggunakan `keydown`. `listener` akan kita isi dengan sebuah fungsi yang akan menambahkan kelas pada elemen html yang sesuai dengan keyboard yang ditekan.

`document.querySelector()` mengembalikan element yang sesuai dengan _selector_ yang telah ditentukan. Dengan begitu,  `audio[data-key="${e.keydown}"]` akan mengambil element audio dengan `data-key` yang sesuai pada `e.keydown`. Begitu juga dengan kelas `key`. `data-key` merupakan sebuah atribut _custom_ yang ada pada elemen html.

`document.querySelectorAll()` sama seperti `querySelector`, namun akan mengembalikan sebuah list element dengan bentuk node. `transitionend` merupakan sebuah event, yang menunjukkan kalau transisi dari css telah selesai.

Demikian penjelasan dari apa yang telah aku pelajari di hari pertama JavaScript30. Untuk teman-teman yang ingin mengetahui penjelasan lengkap dari program ini, bisa kunjungi [javascript30.com](javascript30.com "JS30 by WesBos").

sumber:

* [MDN EventTarget DOM](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget "EventTarget DOM") 
* [MDN EventTarget.addEventListener method](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener "addEventListener on MDN")
* [MDN Event reference](https://developer.mozilla.org/en-US/docs/Web/Events "Event reference")
* [MDN Document.querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector "document.querySelector()")
* [MDN Document.querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll "document.querySelectorAll()")
* [MDN data-* HTML Attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-* "data-* HTML Attribute")