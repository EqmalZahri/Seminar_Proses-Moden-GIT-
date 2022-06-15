[[_TOC_]]

# Latihan 6: GitLab CI/CD
Latihan ini adalah untuk menggunakan GitLab CI/CD


# Langkah 1.0: Tetapan GitLab Runner
Langkah ini adalah untuk membuat tetapan GitLab Runner

* Di laman GitLab, akses ke **mydigital project repository**, dari menu di kiri pilih **Settings -> CI/CD** dan klik **Expand** di senarai **Runners**

<img src="/uploads/3156ad982f609d2a7b29627b6f97187d/image.png" width="700">

<hr>

* Buka aplikasi **Command Prompt**, taip kod berikut untuk akses ke **Cloud Server** seperti yang diberikan

```
ssh root@IP-Address
```

* Masukkan **password** seperti yang di berikan.

* Taip kod berikut untuk **install GitLab Runner**

```
curl -LJO "https://gitlab-runner-downloads.s3.amazonaws.com/latest/deb/gitlab-runner_amd64.deb"

dpkg -i gitlab-runner_amd64.deb
```

* Taip kod berikut untuk pastikan **GitLab Runner** berjaya di **install**

```
gitlab-runner status
```

# Langkah 2.0: CI/CD Pipelines 
Langkah ini adalah untuk menggunakan **GitLab CI/CD Pipelines**

* Di laman GitLab, akses ke **mydigital project repository**

* Dari menu di kiri, pilih **CI/CD -> Pipelines** dan klik **Try test template**

<img src="/uploads/c29b8e85c0fbad8ea1a7314ef90e3f42/image.png" width="700">

<hr>

* Di paparan berikut, klik **Visualize**

<img src="/uploads/57ba46072d5bb3c09f09a4bb70901252/image.png" width="700">

<hr>

* Klik **Edit** dan klik **Commit changes**

<img src="/uploads/00e5f9d3d8edf3056f2c93396e58d555/image.png" width="700">

<hr>

* Dari menu di kiri, pilih **CI/CD -> Pipelines**, berikut adalah contoh paparan.

<img src="/uploads/cfa6e8bbfd73eae48ae5e5ebc4d38bea/image.png" >
