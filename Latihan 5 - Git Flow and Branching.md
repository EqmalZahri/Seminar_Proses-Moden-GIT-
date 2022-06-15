[[_TOC_]]

# Latihan 5: Git Flow & Branching
Latihan ini adalah untuk menggunakan ***Git Flow*** sebagai *Git Branching*

# Langkah 1.0: Git Flow
Latihan menggunakan kaedah ***Git Flow*** untuk Git ***branching***

* Buka aplikasi **Command Prompt** untuk Windows atau **Terminal** untuk MacOS.

Nota: Untuk Windows, buka aplikasi **Command Prompt** dengan menggunakan **Administration mode**

* Wujudkan direktori baru - latihan-5 dan sub-direktori gitflow dengan taip kod seperti berikut

```
mkdir latihan-5
cd latihan-5
mkdir gitflow
cd gitflow
```
* Taip kod berikut untuk *initialize Git Flow*

```
git flow init
```

* Berikut adalah contoh paparan selepas berjaya

```
No branches exist yet. Base branches must be created now.
Branch name for production releases: [master] 
Branch name for "next release" development: [develop] 

How to name your supporting branch prefixes?
Feature branches? [feature/] 
Release branches? [release/] 
Hotfix branches? [hotfix/] 
Support branches? [support/] 
Version tag prefix? [] 
```

* Taip kod berikut untuk pastikan **Master** dan **Develop branch** wujud

```
git branch
```
* Berikut adalah contoh paparan
```
hanafiah > git branch
* develop
  master
```
* Taip kod berikut untuk mulakan fungsi **Git Flow Feature branch**

```
git flow feature start feature-01
```
* Berikut adalah contoh paparan
```
hanafiah > git flow feature start feature-01
Switched to a new branch 'feature/feature-01'

Summary of actions:
- A new branch 'feature/feature-01' was created, based on 'develop'
- You are now on branch 'feature/feature-01'

Now, start committing on your feature. When done, use:

     git flow feature finish feature-01


```
* Taip kod berikut untuk pastikan **feature/feature-01 branch** wujud

```
git branch
```
* Berikut adalah contoh paparan
```
hanafiah > git branch
  develop
* feature/feature-01
  master
```
* Taip kod berikut untuk hentikan fungsi **Git Flow Feature branch**

```
git flow feature finish feature-01
```

* Berikut adalah contoh paparan

```
Switched to branch 'develop'
Already up to date.
Deleted branch feature/feature-01 (was 50a3dd1).

Summary of actions:
- The feature branch 'feature/feature-01' was merged into 'develop'
- Feature branch 'feature/feature-01' has been removed
- You are now on branch 'develop'
```
* Taip kod berikut untuk pastikan **feature/feature-01 branch** tiada dalam senarai

```
git branch
```
* Berikut adalah contoh paparan
```
hanafiah > git branch
* develop
  master
```

# Langkah 2.0: GitHub Flow
Latihan menggunakan kaedah ***GitHub Flow*** untuk Git ***branching***

## Langkah 2.1: Wujudkan *git branch feature*

* Di laman GitLab, akses ke ***myapp project repository***, pilih **New branch** seperti paparan berikut 

<img width="400" alt="image" src="/uploads/ea8c7b2107df31cf7954f976ebca5795/image.png">

<hr>

* Masukkan **feature** untuk **Branch name** dan klik **Create branch**, seperti paparan berikut

<img width="400" alt="image" src="/uploads/f21baa51371e962ecb6b578505ef7ddd/image.png">

<hr>

* Pastikan terdapat 2 **branches - Master and feature** di senarai **Branches** seperti paparan berikut

<img width="400" src="/uploads/db14844801604c58b48f2044fb42bad3/image.png">

<hr>

* Di aplikasi ***Command Prompt*** untuk Windows atau ***Terminal*** untuk MacOS
* Pastikan berada di direktori **myapp**, taip kod berikut untuk lihat ***git branch*** sedia ada

```
git branch
```
* Berikut adalah contoh paparan

```
* master
```

* Taip kod berikut untuk muat turun maklumat terkini dari GitLab

```
git pull
```

* Berikut adalah contoh paparan

```
hanafiah > git pull
From gitlab.com:proses-moden-hanafiah/myapp
 * [new branch]      feature    -> origin/feature
Already up to date.
```

* Taip kod berikut untuk senaraikan **remote branch** di GitLab
```
git branch -a
```
* Berikut adalah contoh paparan

```
* master
  remotes/origin/feature
  remotes/origin/master
```
* Taip kod berikut untuk tukar ke ***feature branch***

```
git checkout feature
```

* Taip kod berikut untuk lihat senarai ***git branch***

```
git branch
```
* Berikut adalah contoh paparan jika berjaya

```
* feature
  master
```

## Langkah 2.2: Fungsi Git *add, commit & push*
* Di aplikasi ***Command Prompt*** untuk Windows atau ***Terminal*** untuk MacOS, taip kod seperti berikut

```
echo "# First Feature" >> uji-branch.md
git add uji-branch.md
git commit -m "tambah fail baru"
git push
```

* Berikut adalah contoh paparan jika berjaya
```
hanafiah > echo "# First Feature" >> uji-branch.md
hanafiah > git add uji-branch.md 
hanafiah > git commit -m "tambah fail baru"
[feature 16c16c8] tambah fail baru
 1 file changed, 1 insertion(+)
 create mode 100644 uji-branch.md
hanafiah > git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 300 bytes | 300.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: To create a merge request for feature, visit:
remote:   https://gitlab.com/proses-moden-hanafiah/myapp/-/merge_requests/new?merge_request%5Bsource_branch%5D=feature
remote: 
To gitlab.com:proses-moden-hanafiah/myapp.git
   ba70e74..16c16c8  feature -> feature
```

* Di laman GitLab, ***myapp project repository***, pilih ***feature branch*** dan pastikan fail **uji-branch.md** wujud di senarai seperti paparan berikut

<img width="915" alt="image" src="/uploads/284febb962a409866095abd0f7ee0f54/image.png">

<hr>

* Sila buat perbandingan di antara ***master branch*** dan ***feature branch***

## Langkah 2.3: Fungsi Git *merge*
* Di laman GitLab, ***myapp project repository***, klik **Create merge request** seperti paparan berikut

<img src="/uploads/5b25800efc61842cbe31797edd834404/image.png">

<hr>

* Masukkan maklumat yang sesuai dan klik **Create merge request** seperti paparan berikut

<img src="/uploads/df95d209a6644786086bfff6197f0710/image.png">

<hr>

* **Uncheked - Delete source branch** dan klik **merge** seperti paparan berikut

<img src="/uploads/a6eb5d896c304dd529e4f4a4e4ab026f/image.png">

<hr>

## Langkah 2.4: Wujudkan *git branch feature-02*

* Di laman GitLab, akses ke ***myapp project repository***, pilih **New branch** 

* Masukkan **feature-02** untuk **Branch name** dan klik **Create branch**, seperti paparan berikut

<img src="/uploads/b5d51f862e8abc3be4cad716a5972856/image.png">

<hr>

* Pastikan terdapat 3 **branches - Master, feature and feature-02** di senarai **Branches** seperti paparan berikut

<img width="400" src="/uploads/033f8214c0038bee69707ee33981a641/image.png">

<hr>

* Di aplikasi ***Command Prompt***
* Pastikan berada di direktori **myapp**, taip kod berikut untuk muat turun maklumat terkini dari GitLab

```
git pull
```

* Berikut adalah contoh paparan

```
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 261 bytes | 130.00 KiB/s, done.
From gitlab.com:proses-moden-hanafiah/myapp
 * [new branch]      feature-02 -> origin/feature-02
   ba70e74..04bef2a  master     -> origin/master
Already up to date.
```

* Taip kod berikut untuk senaraikan **remote branch** di GitLab
```
git branch -a
```
* Berikut adalah contoh paparan

```
* feature
  master
  remotes/origin/feature
  remotes/origin/feature-02
  remotes/origin/master
```
* Taip kod berikut untuk tukar ke ***feature branch***

```
git checkout feature-02
```

* Taip kod berikut untuk lihat senarai ***git branch***

```
git branch
```
* Berikut adalah contoh paparan jika berjaya

```
  feature
* feature-02
  master
```

## Langkah 2.5: *Add, commit & push feature-02 repository* 
* Di aplikasi ***Command Prompt*** untuk Windows atau ***Terminal*** untuk MacOS, taip kod seperti berikut

```
echo "# Second Feature" >> uji-branch-02.md
git add uji-branch-02.md
git commit -m "tambah fail baru"
git push
```

* Berikut adalah contoh paparan jika berjaya
```
hanafiah > echo "# Second Feature" >> uji-branch-02.md
hanafiah > git add uji-branch-02.md
hanafiah > git commit -m "tambah fail baru"
[feature-02 5ebd07f] tambah fail baru
 1 file changed, 1 insertion(+)
 create mode 100644 uji-branch-02.md
hanafiah > git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 328 bytes | 328.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: To create a merge request for feature-02, visit:
remote:   https://gitlab.com/proses-moden-hanafiah/myapp/-/merge_requests/new?merge_request%5Bsource_branch%5D=feature-02
remote: 
To gitlab.com:proses-moden-hanafiah/myapp.git
   04bef2a..5ebd07f  feature-02 -> feature-02
```

* Di laman GitLab, ***myapp project repository***, pilih ***feature-02 branch*** dan pastikan fail **uji-branch-02.md** wujud di senarai seperti paparan berikut

<img width="700" src="/uploads/e1a3c16a815cb2e3c3516dc8d63fa1c0/image.png">

<hr>

* Sila buat perbandingan di antara ***master branch*** dan ***feature branch***

## Langkah 2.6: *Merge branch feature-02* 
* Di laman GitLab, ***myapp project repository***, pilih **Merge request** dari menu disebelah kiri, klik **New merge request** seperti paparan berikut

<img width="700" src="/uploads/469f35b5e204ef7af50c0c6426060ce0/image.png">

<hr>

* Pilih **feature-02** dari senarai **Select source branch**, pilih **master** untuk **Target branch** dan klik **Compare branches and continue** seperti paparan berikut

<img width="700" src="/uploads/a0ef8362f865283e0586a5835c79c3fd/image.png">

<hr>

* Masukkan maklumat yang sesuai dan klik **Create merge request** seperti paparan berikut

<img width="700" src="/uploads/79c567f24fc655bedc6a440932e49228/image.png">

<hr>

* **Uncheked - Delete source branch** dan klik **merge** seperti paparan berikut

<img width="600" src="/uploads/cce833811f5a2920936e2d7abef1efd2/image.png">

<hr>

* Kembali ke ***myapp project repository***, pastikan senarai fail untuk **branch master** dan **feature-02** adalah sama, dan semak juga senarai fail di **branch feature**

# Langkah 3.0: GitLab Flow
Latihan menggunakan kaedah ***GitLab Flow*** untuk Git ***branching***

## Langkah 3.1: Wujudkan *git branch staging*

* Di laman GitLab, akses ke ***myapp project repository***, pilih **New branch** 

* Masukkan **staging** untuk **Branch name** dan klik **Create branch**, seperti paparan berikut

<img width="600" src="/uploads/db0c4e0c06e0019027fa8ae5512c1a65/image.png">

<hr>

* Pastikan terdapat 4 **branches - Master, staging, feature and feature-02** di senarai **Branches**

<hr>

* Di aplikasi ***Command Prompt***
* Pastikan berada di direktori **myapp**, taip kod berikut untuk muat turun maklumat terkini dari GitLab

```
git pull
```

* Berikut adalah contoh paparan

```
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 264 bytes | 264.00 KiB/s, done.
From gitlab.com:proses-moden-hanafiah/myapp
   04bef2a..962b2c7  master     -> origin/master
 * [new branch]      staging    -> origin/staging
Already up to date.
```

* Taip kod berikut untuk senaraikan **remote branch** di GitLab
```
git branch -a
```
* Berikut adalah contoh paparan

```
feature
* feature-02
  master
  remotes/origin/feature
  remotes/origin/feature-02
  remotes/origin/master
  remotes/origin/staging
```

## Langkah 3.2: *Add, commit & push feature-02 repository* 
* Di aplikasi ***Command Prompt*** taip kod seperti berikut

```
echo "# Third Feature" >> uji-branch-03.md
git add uji-branch-03.md
git commit -m "tambah fail ke-3"
git push
```

* Di laman GitLab, ***myapp project repository***, pilih ***feature-02 branch*** dan pastikan fail **uji-branch-03.md** wujud

## Langkah 3.3: *Merge branch feature to staging* 
* Di laman GitLab, ***myapp project repository***, pilih **Merge request** dari menu disebelah kiri, klik **New merge request** seperti paparan berikut

<img width="700" src="/uploads/469f35b5e204ef7af50c0c6426060ce0/image.png">

<hr>

* Pilih **feature-02** dari senarai **Select source branch**, pilih **staging** untuk **Target branch** dan klik **Compare branches and continue** seperti paparan berikut

<img width="700" src="/uploads/07623ae1e043901ddd2f8fadec5bf099/image.png">

<hr>

* Masukkan maklumat yang sesuai dan klik **Create merge request** seperti paparan berikut

<img width="700" src="/uploads/14681bb8fbd5aa3dccc688572f14a6a3/image.png">

<hr>

* **Uncheked - Delete source branch** dan klik **merge** seperti paparan berikut

<img width="600" src="/uploads/516cdf30106115e2bd0facefe345b153/image.png">

<hr>

* Kembali ke ***myapp project repository***, pastikan senarai fail untuk **branch staging** dan **feature-02** adalah sama, dan semak juga senarai fail di **branch master and feature**
