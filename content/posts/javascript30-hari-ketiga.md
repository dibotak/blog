+++
categories = []
date = ""
draft = true
tags = []
title = "JavaScript30: Hari Ketiga"

+++
Pembahasan di hari ini adalah CSS variabel. Jadi, sebenernya CSS itu punya variabel, yang mana sangat memudahkan kita untuk mengganti nilai dari suatu properti, sama seperti variabel pada umumnya.

Dengan bantuan javascript, kita bisa mengganti variabel tersebut. Sehingga tidak perlu merubah satu per satu properti pada masing-masing selektor. Karena nilai dari properti itu sudah diatur oleh CSS variabelnya.

Berikut kodingan yang udah jadi.

    const inputs = document.querySelectorAll('.controls input');
    
    function handleUpdate() {
      const suffix = this.dataset.sizing || '';
      document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
    }
    
    inputs.forEach(input => input.addEventListener('change', handleUpdate));
    inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));

lanjut besok untuk penjelasannya.