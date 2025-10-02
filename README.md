version: "3.8"
services:
  db1:
    container_name: db1
    image: mariadb:latest
    environment:
      - MYSQL_DATABASE=wp_db1
      - MYSQL_USER=casaos
      - MYSQL_PASSWORD=casaos
      - MYSQL_ROOT_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/db1:/var/lib/mysql
      - /var/lib/casaos/apps/db_init/init_db1.sql:/docker-entrypoint-initdb.d/init.sql
    networks:
      - wordpress_net
    restart: always

  db2:
    container_name: db2
    image: mariadb:latest
    environment:
      - MYSQL_DATABASE=wp_db2
      - MYSQL_USER=casaos
      - MYSQL_PASSWORD=casaos
      - MYSQL_ROOT_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/db2:/var/lib/mysql
      - /var/lib/casaos/apps/db_init/init_db2.sql:/docker-entrypoint-initdb.d/init.sql
    networks:
      - wordpress_net
    restart: always

  db3:
    container_name: db3
    image: mariadb:latest
    environment:
      - MYSQL_DATABASE=wp_db3
      - MYSQL_USER=casaos
      - MYSQL_PASSWORD=casaos
      - MYSQL_ROOT_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/db3:/var/lib/mysql
      - /var/lib/casaos/apps/db_init/init_db3.sql:/docker-entrypoint-initdb.d/init.sql
    networks:
      - wordpress_net
    restart: always

  db4:
    container_name: db4
    image: mariadb:latest
    environment:
      - MYSQL_DATABASE=wp_db4
      - MYSQL_USER=casaos
      - MYSQL_PASSWORD=casaos
      - MYSQL_ROOT_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/db4:/var/lib/mysql
      - /var/lib/casaos/apps/db_init/init_db4.sql:/docker-entrypoint-initdb.d/init.sql
    networks:
      - wordpress_net
    restart: always

  db5:
    container_name: db5
    image: mariadb:latest
    environment:
      - MYSQL_DATABASE=wp_db5
      - MYSQL_USER=casaos
      - MYSQL_PASSWORD=casaos
      - MYSQL_ROOT_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/db5:/var/lib/mysql
      - /var/lib/casaos/apps/db_init/init_db5.sql:/docker-entrypoint-initdb.d/init.sql
    networks:
      - wordpress_net
    restart: always

  wordpress1:
    container_name: wordpress1
    image: wordpress:latest
    environment:
      - WORDPRESS_DB_HOST=db1:3306
      - WORDPRESS_DB_NAME=wp_db1
      - WORDPRESS_DB_USER=casaos
      - WORDPRESS_DB_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/wordpress1:/var/www/html
    ports:
      - "8081:80"
    networks:
      - wordpress_net
    restart: always

  wordpress2:
    container_name: wordpress2
    image: wordpress:latest
    environment:
      - WORDPRESS_DB_HOST=db2:3306
      - WORDPRESS_DB_NAME=wp_db2
      - WORDPRESS_DB_USER=casaos
      - WORDPRESS_DB_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/wordpress2:/var/www/html
    ports:
      - "8082:80"
    networks:
      - wordpress_net
    restart: always

  wordpress3:
    container_name: wordpress3
    image: wordpress:latest
    environment:
      - WORDPRESS_DB_HOST=db3:3306
      - WORDPRESS_DB_NAME=wp_db3
      - WORDPRESS_DB_USER=casaos
      - WORDPRESS_DB_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/wordpress3:/var/www/html
    ports:
      - "8083:80"
    networks:
      - wordpress_net
    restart: always

  wordpress4:
    container_name: wordpress4
    image: wordpress:latest
    environment:
      - WORDPRESS_DB_HOST=db4:3306
      - WORDPRESS_DB_NAME=wp_db4
      - WORDPRESS_DB_USER=casaos
      - WORDPRESS_DB_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/wordpress4:/var/www/html
    ports:
      - "8084:80"
    networks:
      - wordpress_net
    restart: always

  wordpress5:
    container_name: wordpress5
    image: wordpress:latest
    environment:
      - WORDPRESS_DB_HOST=db5:3306
      - WORDPRESS_DB_NAME=wp_db5
      - WORDPRESS_DB_USER=casaos
      - WORDPRESS_DB_PASSWORD=casaos
    volumes:
      - /var/lib/casaos/apps/wordpress5:/var/www/html
    ports:
      - "8085:80"
    networks:
      - wordpress_net
    restart: always

networks:
  wordpress_net:
    driver: bridge
