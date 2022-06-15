[[_TOC_]]

# Latihan 9: Pengujian Aplikasi menggunakan Cypress.io
Latihan ini adalah untuk menggunakan GitLab CI untuk membuat pengujian aplikasi menggunakan **Cypress.io**

# Langkah 1.0: NodeJS ***Installation*** 

*  Muat turun aplikasi dan ***install*** nodeJS dari [https://nodejs.org/en/download/](https://nodejs.org/en/download/)
*  Buka aplikasi ***Command Prompt*** untuk Windows atau ***Terminal*** untuk MacOS.

Nota: Untuk Windows, buka aplikasi ***Command Prompt*** dengan menggunakan **Administration mode** 

*  Setelah selesai, di aplikasi ***Command Prompt*** taip kod berikut untuk melihat versi aplikasi node dan npm:
```
node -v
npm -v
```

# Langkah 2.0: _**Initialize**_ Persekitaran NodeJS
Langkah ini adalah untuk initialize NodeJS environment

*  Di aplikasi **Command Prompt**, wujudkan direktori baru - **latihan-9**

```
mkdir latihan-9
cd latihan-9
```
* Taip kod berikut untuk membuka aplikasi **Visual Studio Code**

```
> code .
```
*  Di aplikasi **Visual Studio Code**, buka terminal, dari Menu klik _**Terminal -> New Terminal**_ 
*  Di terminal taip kod seperti berikut

```
> npm init
```

* Berikan maklumat yang sesuai jika perlu, seperti contoh paparan berikut

```
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help init` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (latihan-9) 
version: (1.0.0) 
description: 
entry point: (index.js) 
test command: 
git repository: 
keywords: 
author: 
license: (ISC) 
About to write to /Users/hanafiah/Documents/workshop/jpa/latihan-9/package.json:

{
  "name": "latihan-9",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}


Is this OK? (yes) 
```

* Dari senarai ikon di kiri Visual Studio Code, klik ikon _**Explorer**_ untuk pastikan fail _**package.json**_ wujud

# Langkah 3.0: Cypress.io ***Installation***
*  Di aplikasi ***Command Prompt***, taip kod seperti berikut

```
npm install cypress --save-dev
```

* Di fail **package.json**, pastikan **cypress** adalah salah satu **devDependencies** seperti contoh paparan berikut:

```
{
  "name": "latihan-9",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "cypress": "^10.1.0"
  }
}
```

* Di fail **package.json**. Tukar kod **"script"** dengan salin dan tampal kod berikut

```
"scripts": {
    "cypress:open": "cypress open"
  },
```

* Simpan / **(Save)** fail

# Langkah 4.0: Tetapan Cypress.io

* Di terminal taip kod seperti berikut:

```
npm run cypress:open
```

* Pilih **E2E Testing** dari paparan seperti berikut

<img src="/uploads/6aa464281ca5cf212bb2c42bd96fad24/image.png" width=600>

<hr>

* Pilih **Continue** dari paparan seperti berikut

<img src="/uploads/96fc81ec99899f7cfaef1f594aeea109/image.png" width=600>

<hr>

* Pilih **browser** yang sesuai dan klik **Start E2E Testing in Chrome** dari paparan seperti berikut

<img src="/uploads/40897e38384a4d03aa84e5305f8da7e3/image.png" width=400>

<hr>

* Pilih **Create new empty spec** seperti paparan berikut

<img src="/uploads/147709fe02dfb2858bf9dc2c63aadbf4/image.png" width=600>

<hr>

* Klik **Create spec** seperti paparan berikut

<img src="/uploads/f47acf7a1c03faeaf2209be376e73cc4/image.png" width=400>

<hr>

* Klik **Okay, run the spec** seperti paparan berikut

<img src="/uploads/52337a90ea9a757379fe82c1401d27f3/image.png" width=400>

<hr>

* Berikut adalah contoh paparan jika berjaya

<img src="/uploads/2e9b494d2a7a2005b98f86fd923358c3/image.png" width=600>

<hr>

* Hentikan aplikasi Cypress dengan menutup aplikasi tersebut

# Langkah 5.0: Pengujian Laman Web

* Di Visual Studio Code, buka fail **spec.cy.js** dari direktori **cypress -> e2e**, tukar kod

```
cy.visit('https://example.cypress.io')
```

kepada 

```
cy.visit('https://www.jpa.gov.my')
```

* Simpan / **(Save)** fail

* Di **terminal Visual Studio Code** taip kod seperti berikut:

```
npm run cypress:open
```

* Berikut adalah contoh paparan jika berjaya

<img src="/uploads/a22c23b10f60876c20be3e4614702312/image.png" width=600>

<hr>

* Di fail **spec.cy.js**, padam dan tukar kod kepada berikut

```
describe('empty spec', () => {
  it('passes', () => {
    cy.visit('https://www.jpa.gov.my')
    cy.get(':nth-child(5) > .item-offset > .item-animation > .item-container > .item-content').click()
    cy.get('#cloaka106370d7585b81e558dd8567128d6d3').contains('komunikasi@jpa.gov.my',{ matchCase: true })
  })
})
```
* Simpan / **(Save)** fail

# Langkah 6.0: Wujudkan projek dan muatnaik projeck ke GitLab

* Wujudkan projek baru di GitLab - **e2e test**
* Muat naik projek ke GitLab
* Buat tetapan kepada **GitLab Runner**
* ***Enable*** kan pengujian ***SAST*** dari **Security & Complaince -> Configuration -> SAST**
* Buka fail **.gitlab-ci.yml**, padam dan tukar kod kepada berikut

```
stages:
- test

sast:
  stage: test
include:
- template: Security/SAST.gitlab-ci.yml

local-e2e:
  image: cypress/base:14.16.0
  stage: test
  script:
    - npm ci --prefer-offline
    - npm start &
    - npx cypress run
```
* Klik **Commit changes**, dan perhatikan proses **GitLab Pipelines**
