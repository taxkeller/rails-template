# rails-template

## How to setup

1. Build docker

```
$ docker-compose build
```

2. Build rails app

```
$ docker-compose run --rm web rails new .
```

3. Remove comment out in docker-compose.yml

```
diff --git a/docker-compose.yml b/docker-compose.yml
index a2e8225..40ce510 100644
--- a/docker-compose.yml
+++ b/docker-compose.yml
@@ -15,7 +15,7 @@ services:
     command: ['mysqld', '--character-set-server=utf8mb4']
   web:
     build: .
-    #command: bundle exec rails s -p 3000 -b '0.0.0.0'
+    command: bundle exec rails s -p 3000 -b '0.0.0.0'
     volumes:
       - .:/myapp
```

4. Re-build and start docker containers

```
$ docker-compose up -d --build
```