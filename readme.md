---
title      : "Membangkitkan kunci SSH di Linux"
categories : "Linux"
tags       : "linux command-line ssh"
---

Apa itu SSH? Penjelasan mengenai SSH sendiri di Internet cukup 
banyak, salah satunya di [Wikipedia][1]. 

Untuk membangkitkan pasangan kunci SSH, sebelumnya kita harus 
memasang paket `openssh` dengan perintah

```
# pacman -S openssh
```

<!-- more -->

atau sesuai dengan distro masing-masing. Setelah paket `openssh` 
terpasang, kita dapat membangkitkan (_generate_) pasangan kunci 
SSH dengan perintah

```
$ ssh-keygen -t rsa -C "email@company.com"
```

Baris perintah di atas akan menanyakan lokasi dan nama berkas 
dimana kita ingin menyimpan pasangan kunci. Ketika ditanyakan, 
untuk menggunakan lokasi & nama berkas _default_, tekan `enter` 
tanpa mengisi apapun. Lokasi _default_ untuk pasangan kunci 
adalah `~/.ssh/id_rsa.pub` untuk kunci publik, dan `~/.ssh/id_rsa` 
untuk kunci privat. Kunci privat adalah kunci yang harus dijaga
kerahasiaannya, sebaiknya disimpan dengan aman dan tidak 
memberikannya kepada siapapun. Untuk melihat kunci publik kita 
dapat menggunakan perintah

```
$ cat ~/.ssh/id_rsa.pub
```

Untuk langsung menyalin (_copy_) dapat menggunakan perintah

```
$ xclip -sel clip < ~/.ssh/id_rsa.pub
``` 

Sekian artikel singkat dari saya. Semoga bermanfaat 😊.




[1]: https://en.wikipedia.org/wiki/Secure_Shell