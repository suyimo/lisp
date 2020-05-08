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
 
 brew reinstall nginx-full --with-lua-module --with-upload-module --with-upload-progress-module
 
 
```

```

server {
    listen 8099;
    server_name localhost;

    charset utf-8;
    client_max_body_size 100m;
    
    
    

    location / {
	root /Users/user/nginxStaticFile;
	autoindex on;  
	autoindex_exact_size off;# 显示文件大小
	autoindex_localtime on;# 显示文件时间
	charset utf-8; 
        #index www/pods/index.html www/pods/index.htm www/pods/index.php;
    }

    location /index.html {  
        root /Users/user/nginxStaticFile/www/pods; 
	index index.html;
         
    }

location /upload {
upload_resumable on;
                upload_state_store /Users/user/nginxStaticFile/upload;
            upload_pass /res_upload;
	upload_set_form_field $upload_field_name.path "$upload_tmp_path";
            upload_store /Users/user/nginxStaticFile;
        }
        location /res_upload {
            default_type text/html;
            return 200 URL;
        }

} 


```


https://www.cnblogs.com/valu/p/10808229.html
https://tsov.net/uupee/22628/
https://www.jianshu.com/p/ef9f75094a65
