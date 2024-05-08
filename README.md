# TUTORIAL 10 ADPRO
#### Rafi Ghani Harditama (2206081364)
#### ADPRO A / VRO


## Understanding how it works
![alt text](image.png)

Dari gambar diatas, dapat dilihat bahwa output pertama yang muncul adalah `Rafi Ghani's Komputer: hey hey!` kemudian baru perintah yang berada di spawner muncul. Hal ini terjadi karena eksekusi tugas yang dijadwalkan `(spawner.spawn(...))` dilakukan secara asynchronous/tidak dijalankan saat itu juga. Jadi ketika `Rafi Ghani's Komputer: hey hey!` dijalankan,  executor belum mulai mengeksekusi tugas yang dijadwalkan, sehingga pesan tersebut muncul terlebih dahulu sebelum pesan dari tugas yang dijadwalkan.

## Multiple Spawn and removing drop.
Multiple Spawn
![alt text](image-1.png)

Removing drop
![alt text](image-2.png)

Adding drop again
![alt text](image-3.png)

Dari gambar-gambar diatas, dapat kita lihat terdapat task-task yang dijadwalkan untuk dieksekusi melalui spawner dan executor yang mengatur eksekusi task-task tersebut. Saat `drop(spawner)` digunakan, executor mengetahui bahwa tidak ada lagi task baru yang akan dikirim sehingga langsung berhenti setelah menyelesaikan semua task dalam antrian. Namun, jika `drop(spawner)` dihapus, executor akan terus berjalan dan menunggu task baru yang tidak akan datang.