# How to connect Laravel with Quasar

## Directory structure

 - `/` - Laravel application root folder.
 - `/admin` - Quasar admin application root folder;
 - `/public` - The HTTP server URL root is pointing to this directory.
 - `/public/admin` - Quasar admin application will be build in this directory.
 - `/public/admin/index.html` - Quasar admin application entry point.

## Prepare

1. Create fresh laravel
```bash2
$ laravel fresh laravel-app
```

2. Change directory to laravel folder
```bash2
$ cd laravel-app
```

3. Install Quasar
```bash2
$ quasar create admin
```

4. Configure quasar. Add following lines to your `/admin/quasar.conf.js` file:
```
     build: {
+      distDir: '../public/admin/',
+      publicPath: 'admin/',
       scopeHoisting: true,
```

5. Add following line to your `/.gitignore` file
```
/public/admin
```

6. Remove following line to your `/admin/.gitignore` file
```
/dist
```

7. Configure `.htaccess` file
```
TODO
```

## Development

1. Run Laravel server
```bash2
$ php artisan serve
```

2. Run Quasar dev server
```bash2
$ cd admin
$ quasar dev
```

## Build for production

This commands will build your Quasar application into `/public/admin` directory.

```bash2
$ cd admin
$ quasar build
```
