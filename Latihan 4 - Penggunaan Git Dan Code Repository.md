[[_TOC_]]


# Latihan 4 : Penggunaan Git Dan Code Repository
Latihan ini adalah untuk memahami penggunaan git bersama GitLab ***code repository***



## Langkah 1.0: Git Clone untuk projek GitLab sedia ada
Latihan menggunakan ***command Git clone*** untuk projek GitLab sedia ada

* Buka aplikasi **Command Prompt** untuk Windows atau **Terminal** untuk MacOS.

Nota: Untuk Windows, buka aplikasi **Command Prompt** dengan menggunakan **Administration mode**

* Wujudkan direktori baru - latihan-4 dengan taip kod seperti berikut

```
mkdir latihan-4
cd latihan-4

```

### Langkah 1.1: Tetapan Git untuk GitLab

* Taip kod berikut untuk membuat tetapan Git - projek GitLab kepada direkotri latihan-4, sila tukar maklumat yang sesuai

```
git config --local user.name "GitLab ID/Name"
git config --local user.email "Email to access GitLab"

```

### Langkah 1.2: Clone projek GitLab

* Akses ke projek **mydigital**, klik **Clone** dan klik **Copy URL** dari **Clone with HTTPS** untuk salin maklumat seperti paparan

<img src="/uploads/49dd2bbef384e7fa0d9c6e68545ddf3a/image.png" width=400>

<hr>

* **Clone** projek **mydigital** dengan taip kod seperti berikut di aplikasi **Command Prompt**

```
git clone https://gitlab.com/proses-moden/mydigital.git
cd mydigital
```

* Taip kod berikut untuk buka **Micorosoft Visual Studio Code**

```
code .
```

* Di **Visual Studio Code** wujudkan fail baru - **latihan-4.md** seperti paparan berikut

<img src="/uploads/6f57dced76135c8fc9c105bd1d1b240f/image.png" width=300>

<hr>

* Salin tan tampal kod berikut ke fail baru

```
# Latihan-4
Latihan DevOps GitLab untuk ***Git clone*** dan ***code repository***

```
* Simpan / (**Save**) fail. Sila rujuk paparan berikut:

<img src="/uploads/2bfea1abe4902fdf231d546914e2713f/image.png">

<hr>

* Di aplikasi **Command Prompt**, taip kod seperti berikut untuk muat naik maklumat ke GitLab

```
git add .
git commit -m "Tambah fail latihan-4"
git push

```

* Berikut adalah cotoh paparan jika berjaya

```
hanafiah > git add .
hanafiah > git commit -m "Tambah fail latihan-4"
[main 3588d43] Tambah fail latihan-4
 1 file changed, 2 insertions(+)
 create mode 100644 latihan-4.md
hanafiah > git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 356 bytes | 356.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://gitlab.com/proses-moden/mydigital.git
   4fcac59..3588d43  main -> main
```

* Di GitLab, **Refresh** laman projek **mydigital**, dan pastikan fail baru **latihan-4.md** di senarai fail projek seperti contoh paparan berikut

<img src="/uploads/048a819165f051ab90b4e53731b94ed3/image.png" width=600>

<hr>

## Langkah 2.0: Muatnaik local projeck ke GitLab
Latihan menggunakan ***command Git*** untuk muatnaik projek sedia ada ke GitLab

### Langkah 2.1: Wujudkan projek di komputer

* Di aplikasi **Command Prompt**, taip kod seperti berikut untuk wujudkan direktori baru

Nota: pastikan direktori baru ini di bawah direktori **latihan-4** seperti langkah sebelum ini

```
mkdir myapp
cd myapp
```

* **Initialize git** dengan taip kod berikut

```
git init

```

* Pastikan direktori baru **.git** wujud

* Taip kod berikut untuk buka **Micorosoft Visual Studio Code**

```
code .
```

* Di **Visual Studio Code** wujudkan fail baru - **README.md** seperti paparan berikut


* Salin dan tampal kod berikut ke fail baru

```
# Latihan-4
Latihan DevOps untuk muatnaik **local repoitory** ke GitLab

```
* Simpan / (**Save**) fail.


### Langkah 2.2: Wujudkan Projek baru di GitLab 
Langkah ini adalah untuk mewujudkan projek baru di GitLab

*  Di laman GitLab anda, klik ***New Project*** untuk mewujudkan projek baru

*  Di paparan ***Create new project***, pilih ***Create blank project***

*  Masukkan **myapp** di ***Project name***, pilih **proses-moden** di ***Project URL***, pilih ***Private*** untuk ***Visibility Level***, ***unchecked*** di ***Initialize repository with a README*** seperti dipaparan berikut dan klik ***Create project*** 

<img src="/uploads/0c1020501a8d447fca55a960d3c596e8/image.png">

<hr>

*  Berikut adalah paparan setelah berjaya

<img src="/uploads/d9f3df5b812c32ad47720e2abbe665c0/image.png">

<hr>

### Langkah 2.3: Muatnaik *local repository* ke projek GitLab 
Langkah ini adalah untuk muatnaik local repository ke projek GitLab

* Di aplikasi **Command Prompt**, taip kod seperti berikut

```
git remote add origin https://gitlab.com/proses-moden/myapp.git
git add .
git commit -m "Initial commit"
git push -u origin master
```

* Berikut adalah contoh maklumat jika berjaya

```
hanafiah > git remote add origin https://gitlab.com/proses-moden/myapp.git
hanafiah > git add .
hanafiah > git commit -m "Initial commit"
[master (root-commit) d0d6a50] Initial commit
 1 file changed, 2 insertions(+)
 create mode 100644 README.md
hanafiah > git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 281 bytes | 281.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To gitlab.com:proses-moden/myapp.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

```
* Di GitLab, **Refresh** laman projek **myapp**, dan pastikan fail baru **README.md** di senarai fail projek seperti contoh paparan berikut

<img src="/uploads/56d2883ce2944262fe54035b998f2050/image.png" width=600>

