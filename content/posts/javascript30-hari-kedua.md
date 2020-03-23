+++
categories = ["Pemrograman"]
date = 2020-03-23T15:50:00Z
tags = ["javascript", "catatan teknis"]
title = "JavaScript30: Hari Kedua"

+++
Di hari kedua ini, aku belajar membuat jam analog. Oiya, sebelumnya aku lupa ngasih tau kalo di JS30 ini udah disediain bahan-bahannya, jadi kita tinggal fokus aja ke belajar vanilla javascriptnya.<!--more-->

Lanjut, langsung aja ini dia kodingan yang udah jadi.

    const secondHand = document.querySelector('.second-hand');
    const minHand = document.querySelector('.min-hand');
    const hourHand = document.querySelector('.hour-hand');
    
    function setDate() {
      const now = new Date();
      const seconds = now.getSeconds();
      const secondDegree = (seconds / 60) * 360 + 90;
      
      const minutes = now.getMinutes();
      const minutesDegree = (minutes / 60) * 360 + 90;
    
      const hours = now.getHours();
      const hoursDegree = (hours / 12) * 360 + 90;
      secondHand.style.transform = `rotate(${secondDegree}deg)`;
      minHand.style.transform = `rotate(${minutesDegree}deg)`;
      hourHand.style.transform = `rotate(${hoursDegree}deg)`;
    }
    
    setInterval(setDate, 1000);

Dari bahan yang udah disediain itu, terdapat beberapa `div` yang akan diotak-atik. Yang paling penting ada 3, yaitu jarum jam, jarum menit dan jarum detik, yang ditandai dengan tambahan kelas `second-hand`, `min-hand`, dan `hour-hand`.

**Algoritma**

Setiap detik jarum jam akan diubah dengan menggunakan fungsi `setInterval`. Namun sebelum itu kita akan membuat suatu fungsi yang akan dipanggil pada setiap interval.

Fungsi ini akan mengubah rotasi jarum jam, waktu yang digunakan adalah waktu sekarang. Dibuatlah objek baru yang bernama `new`, yang isinya diambil dari _built-in object_ `Date`, untuk mengetahui waktu saat ini.

Method `getSeconds`, `getMinutes`, dan `getHours` digunakan untuk mengambil nilai detik, menit, dan jam. Kemudian dibuat variabel baru pada masing-masing satuan waktu untuk dijadikan sebagai patokan derajat. Baru setelah itu setiap jarum petunjuk style `transform`nya diubah.

Jadi deh, jam analog pada web. Pelajaran yang bisa diambil, ya jadi tau penggunaan _built-in object_ `Date`. Juga pembiasaan untuk mengubah tampilan web dengan javascript, perlahan-lahan jadi tau cara kerja dibalik sebuah tampilan web.

Sekian, dan terimakasih.

Referensi:

> Silahkan sering-sering baca dokumentasi kalo gak ngerti. Di google banyak.