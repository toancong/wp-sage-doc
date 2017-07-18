
## How to create a theme by Sage

1. Add a service docker
```
  wp-theme:
    image: toancong/wp-sage:sage8.5
    volumes:
      - ./wp-content/themes:/usr/source
```

2. Create a your theme
```
docker-compose run --rm wp-theme composer create-project roots/sage your-theme-name 8.5.1
```

3. Install dependency packages for develop theme
```
docker-compose run --rm wp-theme bash -c "cd your-theme-name && npm install && bower install --allow-root"
```

Step 2 & 3 can become
```
docker-compose run --rm wp-theme bash -c "composer create-project roots/sage your-theme-name 8.5.1 && cd your-theme-name && npm install && bower install --allow-root"
```

4. See the theme in your backend `/wp-admin/themes.php`
