# Advanced npm

```sh
npm install express

# Ohter possiblities
npm install https://github.com/strongloop/express
npm install https://www.myserver.com/package1

# Hem js dosyası hemde package.json dosyası bulunmalıdır.
# https://gist.github.com/joeeames/58e5dfc62489a5a288de
npm install gist:58e5dfc62489a5a288de
```

```sh
# Installing from a Folder
# For closed source company internal packages
npm install nas:/path/to/package

# npm in sitesinden de bulunarak indirilebilir.
https://www.npmjs.com/search?q=underscore
```

```sh
# Daha önce indirilmiş fakat package.json dosyasında bulunmayan paketleri siler.
npm prune

# Administrator olarak çalıştırarak npm in kendisini güncelleyebiliriz.
npm install npm@latest -g
```


```sh
# package.json dosyasında bulunan script leri aşağıdakine benzer şekilde çalıştırabiliriz.
npm run test
npn run start
```

```json
{
    "scripts": {
        "start": "node server.js",
        "test": "node test.js"
    }
}
```

```sh
# Known security vulnerabilities audit
# Hepsini fix edemeyebilir. Fakat önemli ölçüde yardımcı olur.
npm audit fix
```