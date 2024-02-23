# Manual de Instalación: Linux | Valet

## Requisitos Previos

- Acceso root al servidor local Linux.
- Instalación de PHP 7.2 y las librerías requeridas por el aplicativo y Laravel.
- Instalación de MySQL (opcionalmente, PhpMyAdmin) para pruebas de base de datos.
- Instalación de Git, Curl, Composer.

## Pasos de Instalación

### 1. Configuración de PHP en Ubuntu

```bash
apt-get update
apt-get install software-properties-common
apt-get install python-software-properties
add-apt-repository ppa:ondrej/php
apt-get update
apt-get install php7.2 php7.2-mbstring php7.2-soap php7.2-zip php7.2-mysql php7.2-curl php7.2-gd php7.2-xml php7.2-mcrypt
```

### 2. Instalación de MySQL y PhpMyAdmin

```bash
apt-get install mysql-server-5.7 mysql-client-5.7 phpmyadmin
```

### 3. Instalación de Curl, Git y Composer

```bash
apt-get install git
apt-get install curl
apt-get install composer
chmod -R 777 ~/.composer
```

### 4. Instalación de Valet y Configuración

```bash
composer global require cpriego/valet-linux
nano ~/.profile
# Añadir al final: PATH= "HOME/.composer/vendor/bin:$PATH"
source ~/.profile
apt install network-manager libnss3-tools jq xsel
services apache2 stop
apt install nginx
systemctl status nginx
valet install
mkdir ~/code
cd code
valet park
```

### 5. Clonar Repositorio y Configurar

```bash
git clone https://gitlab.com/b.mendoza/facturadorpro3.git
cd facturadorpro3
cp .env.example .env
```

Configurar el archivo `.env` con la URL base, nombre de la base de datos, usuario y contraseña.

### 6. Configuración Adicional

```bash
php artisan key:generate
composer dump-autoload
```

Registrar la base de datos mediante PhpMyAdmin en `sudominio.com/phpmyadmin` con el usuario root y contraseña.

### 7. Paquetes y Migraciones

```bash
composer install
php artisan migrate --seed
```

### 8. Verificación y Ajustes

- Verificar en PhpMyAdmin la creación de la base de datos y tablas.
- Ajustar permisos en carpetas del proyecto con:
  ```bash
  chmod -R 755 storage
  chmod -R 755 bootstrap/cache
  ```

### 9. Establecer Rutas y Acceder

```bash
php artisan storage:link
```

### 10. Accesos

- [Facturadorpro3.test](Facturadorpro3.test)
- Usuario: admin@gmail.com
- Contraseña: 123456

¡Listo para utilizar el Facturador en su dominio!
