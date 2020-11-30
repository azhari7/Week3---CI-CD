# Week3---CI-CD

1. Konfugurasi Reverse Proxy. disini domain cicd.azhari.insturctype.com akan diarahkan ke ip private Jenkins!!
![alt text](https://github.com/azhari7/Week3---CI-CD/blob/master/Asset/aws-07-config%20reverse%20proxycicd.jpg.png)

2. instalasi docker penambahan repo, update package kemudian jalankan command apt install docker-ce docker-ce-cli containerd.io
3. Dockerize aplikasi
   - Buat file Dockerfile pada folder yang akan di build menjadi image
   - docker build -t azhari7/dumbways-frontend .
   - docker run -it -p 3000:3000 -d azhari7/dumbways-frontend
   
4. Instalasi docker jenkins
   - sudo docker run -ti -p 8080:8080 -p 50000:50000 -v /ubuntu/home/:/var/jenkins_home -d jenkins/jenkins
5. Generate API key, API key digunakan untuk webhook github kemudian Enable remote proxy
6. CI dengan Pipeline, create job -> pilih pipeline
7. Berikut adalah stage pipeline jobs
    - Stage Checking git untuk pull git dan branc yang akan di build
    - Stage Dockerize untuk build docker image
    - Stage Docker Push
    - Stage  Deploy frontend server untuk deploy ke server remote
8. Lakukan pengecekan pada stage view dan docker registry
9. Penambahan webhook pada github
    - webhook :user:pass@cicd.azhari.instructype.com/job/dumbplay-backend/build?token=tokerAPI
    - testing modif source code




