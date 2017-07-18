
## How to create a theme by Sage

### Add a service docker
```
  wp-theme:
    image: toancong/wp-sage:sage9
    volumes:
      - ./wp-content/themes:/usr/source
```

### Create a your theme

#### Sage 8.5
```
docker-compose run --rm wp-theme bash -c "composer create-project roots/sage your-theme-name 8.5.1 && cd your-theme-name && npm install && bower install --allow-root"
```

#### Sage 9
```
docker-compose run --rm wp-theme bash -c "composer create-project roots/sage green-island dev-master && cd green-island && yarn"
````

See the theme in your backend `/wp-admin/themes.php`
