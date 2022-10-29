# Publishing Your Own Package

* Set up your npm user for publishing
  * Sign up for an account at npmjs.com
  * Authentication token alınıp, npm.rc dosyasına yazılır.

* Preparing your project for publishing
  * Github a repo publish edilir.
  * npm init ile projeye package.json dosyası oluşturulur. Ki kullanacak olan kişiler kütüphanenin ne olduğunu anlayabilsinler.

* Publishing your package
  * "npm publish" komutu ile publish edilir.

* Publishing updates
  * "npm version patch", "npm version minor", "npm version major" ile versiyon güncellemesi yapılır.
  * "npm publish" ile publish edilir.

* Beta releases
  * "npm publish --tag beta" ile beta olarak publish edilir.
  * "npm install my-package@beta" ile beta versiyonu indirilir.
  * "version": "1.0.0-beta.1" şeklinde package.json dosyasında belirtilir.