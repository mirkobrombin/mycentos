# Brotli

## Nginx module
```
mkdir /usr/lib64/nginx/modules
cd /usr/lib64/nginx/modules
wget --no-cache https://www.mysterydata.com/upload/nginx-brotli-modules.zip
unzip nginx-brotli-modules.zip
rm -rf nginx-brotli-modules.zip
```
### Configuration
Add modules on top of `/etc/nginx/nginx.conf`:
```
load_module "modules/ngx_http_brotli_filter_module.so";
load_module "modules/ngx_http_brotli_static_module.so";
```
configure brotli compression on `http{..}` block:
```
# Compression brotli
    brotli              on;
    brotli_comp_level   6;
    brotli_static       on;
    brotli_types        text/xml image/svg+xml application/x-font-ttf image/vnd.microsoft.icon application/x-font-opentype application/json font/eot application/vnd.ms-fontobject application/javascript font/otf application/xml application/xhtml+xml text/javascript  application/x-javascript text/plain application/x-font-truetype application/xml+rss image/x-icon font/opentype text/css image/x-win-bitmap;
    ```
