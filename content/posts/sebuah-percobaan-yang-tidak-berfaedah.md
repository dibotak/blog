+++
categories = ["Pemrograman"]
date = 2020-10-10T15:12:00Z
tags = ["javascript"]
title = "Sebuah Percobaan yang Tidak Berfaedah"

+++
Jadi pada malam ini aku sedang membuat suatu aplikasi, tapi ternyata muncul sebuah bug dan aku sedang malas untuk menanganinya. Jadilah tercetus sebuah keisengan, yaitu membuat fungsi yang mengembalikan fungsi, berikut kodenya:<!--more-->

(mungkin ini bisa digunakan untuk belajar rekursif)

    function pertama(param) {
      console.log(`nilai pertama: ${param}`);
      return function (param2) {
        console.log(`nilai kedua: ${param2}`);
        return function (param3) {
          console.log(`nilai ketiga: ${param3}`);
          return function (param4) {
            console.log(`nilai keempat: ${param4}`);
            return function (param5) {
              console.log(`nilai kelima: ${param5}`);
              return function (param6) {
                console.log(`nilai keenam: ${param6}`);
                return function (param7) {
                  console.log(`nilai ketujuh: ${param7}`);
                  return function (param8) {
                    console.log(`nilai kedelapan: ${param8}`);
                    return function (param9) {
                      console.log(`nilai kesembilan: ${param9}`);
                      return function (param10) {
                        console.log(`nilai kesepuluh: ${param10}`);
                        return param + param2 + param3 + param4 + param5 + param6 + param7 + param8 + param9 + param10;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    
    console.log(pertama(1)(2)(3)(4)(5)(6)(7)(8)(9)(10));

Sangat tidak berfaedah bukan? Tapi dengan aku membuat hal ini terjadi, ada kesenangan yang mungkin hanya aku saja yang paham. Sekian tulisan penghibur malam ini, sampai jumpa di tulisan lainnya!