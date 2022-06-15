[[_TOC_]]

# Latihan 8: Pengujian Keselamatan
Latihan ini adalah untuk menggunakan GitLab untuk membuat pengujian keselamatan kepada projek **repository*

# Langkah 1.0: Wujudkan Projek 
Langkah ini adalah untuk mewujudkan projek baru di GitLab

*  Di laman GitLab anda, klik ***Menu -> Projects -> Create new project*** untuk mewujudkan projek baru

*  Di paparan ***Create new project***, pilih ***Create blank project***

<img src="https://code.cloud-connect.asia/researchproject/continues-integration-and-delivery/documents/uploads/86a69815554a82c32ebcc729cd7ae848/image.png" width="500">

<hr>

*  Masukkan **mysecure-app** di **Project name**, pilih akaun anda di **Project URL**, pilih **Private** untuk **Visibility Level**, **unchecked** di **Initialize repository with a README**, **checked** di **Enable Static Application Security Testing (SAST)** seperti dipaparan berikut dan klik **Create project** 

<img src="/uploads/750a933528a8857b51aa78b000b035c9/image.png" width="600">

<hr>

*  Berikut adalah paparan setelah berjaya dan pastikan fail **.gitlab-ci.yml**

<img src="/uploads/1dc8eaef8882f720e291fc3d987a358e/image.png">

<hr>

*  Buka fail **.gitlab-ci.yml** seperti contoh paparan berikut

<img src="/uploads/8600e2594121317dc58bc0f5da7df4d3/image.png">

<hr>

# Langkah 2.0: Ujian Keselamatan aplikasi javascript

* Wujudkan fail baru -**index.js**, salin dan tampal kod berikut

```
console.log("Latihan DevOps")
```

* klik **Commit changes** seperti contoh paparan berikut

<img src="/uploads/94232a2c59ca94b6f929403c7126e35e/image.png">

<hr>

* Pilih **CI/CD -> Pipelines** dari menu di kiri dan pastikan terdapat proses CI dari senarai **Pipelines** seperti contoh paparan berikut

* klik **Commit changes** seperti contoh paparan berikut

<img src="/uploads/91435bf3e92a7a081d0e0f277817c96d/image.png">
