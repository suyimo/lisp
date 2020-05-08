# lisp

```
http://nginx.org/en/download.html   1.18.0
git clone -b 2.3.0 https://github.com/vkholodkov/nginx-upload-module.git
 git clone https://github.com/masterzen/nginx-upload-progress-module.git
 git clone -b OpenSSL_1_0_2d https://github.com/openssl/openssl.git
 https://ftp.pcre.org/pub/pcre/
 ./configure --add-module=/Users/user/git/lisp/nginx_file/nginx-upload-module --add-module=/Users/user/git/lisp/nginx_file/nginx-upload-progress-module  --with-openssl=/usr/local/Cellar/openssl/1.0.2q
 
 
 brew uninstall nginx
 brew tap denji/nginx 
 brew install nginx-full --with-upload-module --with-upload-progress-module
 
 brew services start denji/nginx/nginx-full
```


