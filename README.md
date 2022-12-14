![IDESA LOGO](https://www.idesa.com.py/img/iconos/logo_idesa.png)
#IDESA Desafío Developer:
*Diseño de un REST API en PHP, usando Laravel, con base de datos mysql.*

#Proyecto: Naguarabit API

##Resumen Stack usado:
Mysql/MariaDB
Laravel
PHP 

###Detalles del entorno desarrollo:
PHP version: 7.4
Laravel version: 8.83.26
Database: 10.3.20-MariaDB - mariadb.org binary distribution
User: root@localhost

###WAMPP Server:
Apache/2.4.41 (Win64) OpenSSL/1.1.1c PHP/7.4.0
Versión del cliente de base de datos: libmysql - mysqlnd 7.4.0
extensión PHP: mysqliDocumentación curlDocumentación mbstringDocumentación

###Requerimientos:
PHP version: 7.4 o superior
Composer
Mysql



##Pasos para montar el aplicativo:

1. clonar repositorio:
https://github.com/gabdevpy/idesa-api-demo-naguarabit

2. descargar y restaurar backup de base datos del repositorio, ubicado en database/backup/:
https://github.com/gabdevpy/idesa-api-demo-naguarabit/blob/master/database/backup/production_naguarab_backend__2022-11-18_13-32-50.sql

3. revisar configuracion en archivo .env.
Modificar solo si hace falta, por ejemplo, para ajustar parametros conexion bd acorde al servidor/entorno.
DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=new_naguarabit
DB_USERNAME=root
DB_PASSWORD=

4. Ejecutar siguientes comandos:
$ composer install
$ php artisan optimize:clear
$ composer dump-autoload
$ php artisan migrate
$ php artisan db:seed
$ php artisan jwt:secret
$ php artisan serve



##**API TESTING**:
-El archivo route_list_api.txt contiene el listado de todos los endpoints, algunos no están implementados al 100%.
Las rutas que expongo para este demo son:
country
banks

##**Ejemplos operaciones GET**
*http://localhost:8000/api/countries/ (lista todos los paises)
*http://localhost:8000/api/banks/show/1 (consulta un bancos por id 1)
*http://localhost:8000/api/banks (lista todos los bancos sin importar su estatus activo o inactivo)
*http://localhost:8000/api/banks/PAR/byCountry (lista todos los bancos de un pais especifico: PARAGUAY)
*http://localhost:8000/api/banks/VEN/byCountry (lista todos los bancos de un pais especifico: Venezuela)
*http://localhost:8000/api/banks/VEN/byActive (lista todos los bancos con estatus activo)
