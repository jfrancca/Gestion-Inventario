# Getión de Inventario

📦 Sistema de API para Getión de Inventario con sistemas de autenticación con roles.

## 🚀 Tecnologías
- **Lenguaje**: php 8.4.5
- **Framework UI**: Laravel 12
- **Docker** Laravel sail
- **Composer** Gestión de paquetes
- **Arquitectura**: MVC (Model-View-Controlador)
- **Paquetes**: Laravel Sanctum autenticación con token, spatie para gestión de roles, laravel-lat-es paquete para traducción en laravel y dar claridad a los mensajes de respuesta para el usuario.
- **Pruebas**: Postman
- **Despliegue**: Laravel cloud

## 🧑‍💻 Autenticación
- Login con JWT o Laravel Sanctum.

## 👮 Roles y Permisos (Spatie)
- Los roles se gestionan con spatie.
- Seeders crean usuarios con roles (admin, user).
- Tabla pivot model_has_roles se llena automáticamente al registrar.

## 📚 Librerías usadas
- Laravel Sail.
- Spatie Laravel.
- Laravel Sanctum.

## 📬 Endpoints

| Método | Ruta                          | Descripción                            |
|--------|-------------------------------|----------------------------------------|
| POST   | /api/register                 | Registro de usuarios                   |
| POST   | /api/register-whit-role       | Registro con rol                       |
| POST   | /api/login                    | Login de usuarios                      |
| POST   | /api/categories               | Crear categorías de productos          |
| POST   | /api/products                 | Crear productos                        |
| GET    | /api/products                 | Consultar lista de productos           |
| GET    | /api/products/{id}            | Consultar detalle de un producto       |
| PUT    | /api/products/{id}            | Actualizar producto                    |
| DELETE | /api/products/{id}            | Eliminar producto                      |
| POST   | /api/logout                   | Cerrar sesión                          |


## ⚙️ Instrucciones para configurar localmente

```bash
git clone https://github.com/jfrancca/Gestion-Inventario.git

cd Gestion-Inventario

cp .env.example .env

docker run --rm \
    -v $(pwd):/opt \
    -w /opt \
    laravelsail/php82-composer:latest \
    composer install

alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'

sail up

sail artisan key:generate

Editar .env
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=GestionInventario
DB_USERNAME=sail
DB_PASSWORD=password

sail artisan migrate

sail artisan db:seed
```

## Cómo importar y usar la colección Postman

```bash
Después de tener intalado Postman, elegir importar, seleccionar archivo y 
elegir los archivos adjuntos al correo, son dos, uno para la pruebas en 
el ambiente local y el otro para el productivo.
```

## URL pública de despliegue

```bash
https://gestion-inventario-main-j7erae.laravel.cloud
```

