[[_TOC_]]

# Latihan 7: Stress Test Laman Web
Latihan ini adalah untuk menggunakan **GitLab CI Pipelines** untuk membuat **stress test** dengan aplikasi **K6** kepada laman Web

# Langkah 1.0: Wujudkan fail ujian K6

* Di laman GitLab, akses ke **mydigital project repository**, wujudkan fail baru **stress-test-jpa.js**, salin dan tampal kod berikut, dan klik **Commit changes**

```
import { sleep } from 'k6';
import http from 'k6/http';

export const options = {
  duration: '1m',
  vus: 50,
  thresholds: {
    http_req_duration: ['p(95)<500'], // 95 percent of response times must be below 500ms
  },
};

export default function () {
  http.get('https://www.jpa.gov.my');
  sleep(3);
}
```

# Langkah 2.0: Stress Test menggunakan K6

* Edit fail **gitlab-ci.yml**, padam dan tukar kod kepada berikut dan klik **Commit changes**

```
stages:
  - build
  - deploy
  - loadtest-local

image:
  name: ubuntu:latest

build:
  stage: build
  script: 
    - echo "building my application in ubuntu container..."

deploy:
  stage: deploy
  script: 
    - echo "deploying my application in ubuntu container..."

loadtest-local:
  image:
    name: loadimpact/k6:latest
    entrypoint: [""]
  stage: loadtest-local
  script: 
    - echo "executing local k6 in k6 container..."
    - k6 run stress-test-jpa.js
```
* Dari menu di kiri, pilih **CI/CD -> Pipelines** dah lihat senarai terkini seperti contoh paparan

<img src="/uploads/2651eeee8b1898a8de12fb6564aaf9b3/image.png">

<hr>

* Klik dari senarai terkini seperti contoh paparan

<img src="/uploads/31d17e845d18f5dc5eb0c38275cbddb0/image.png">

<hr>

* Klik **loadtest-local** untuk melihat maklumat terperinci **stress test using k6*

<img src="/uploads/6823076068ebde2ab61603c3fa5faf4c/image.png">

<hr>
