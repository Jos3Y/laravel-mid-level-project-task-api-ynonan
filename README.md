# laravel-mid-level-project-task-api-ynonan
Prueba
API RESTful de Gestión de Proyectos y Tareas
Requisitos del sistema
- PHP >= 8.1
- Composer
- Laravel 10
- MySQL o cualquier base de datos compatible con Laravel
- Extensiones PHP: OpenSSL, PDO, Mbstring, Tokenizer, XML, Ctype, JSON, BCMath
- Node.js y npm (opcional para frontend o assets)
- Laravel Telescope y L5-Swagger instalados vía Composer
Instalación paso a paso
1. Clonar el repositorio
```bash
git clone https://github.com/tu_usuario/laravel-mid-level-project-task-api-tu_nombre.git
cd laravel-mid-level-project-task-api-tu_nombre
```

2. Instalar dependencias con Composer
```bash
composer install
```

3. Crear archivo `.env` copiando el ejemplo
```bash
cp .env.example .env
```

4. Configurar las variables de base de datos en `.env`
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nombre_de_tu_base
DB_USERNAME=tu_usuario
DB_PASSWORD=tu_password
```

5. Generar la clave de la aplicación
```bash
php artisan key:generate
```

6. Ejecutar migraciones y seeders si aplica
```bash
php artisan migrate
```

7. Levantar el servidor local
```bash
php artisan serve
```
Cómo levantar Swagger
1. Accede a la documentación generada en:
http://localhost:8000/api/documentation

2. Para actualizar la documentación después de cambios:
```bash
php artisan l5-swagger:generate
```
Cómo ver Laravel Telescope
1. Asegúrate que el entorno está en `local` en `.env` (APP_ENV=local).
2. Visita:
http://localhost:8000/telescope
3. Allí podrás monitorear consultas, logs, solicitudes HTTP, excepciones y más.
Cómo probar filtros dinámicos
En Proyectos (`/api/projects`):
- Filtrar por estado:
`GET /api/projects?status=active`

- Buscar por nombre parcial:
`GET /api/projects?name=api`

- Filtrar por rango de fechas (created_at):
`GET /api/projects?date_from=2024-01-01&date_to=2024-04-01`
En Tareas (`/api/tasks`):
- Filtrar por estado y prioridad:
`GET /api/tasks?status=pending&priority=high`

- Filtrar por fecha de vencimiento y proyecto:
`GET /api/tasks?due_date=2024-05-30&project_id=uuid-del-proyecto`
Cómo ver logs de auditoría
- Los logs de auditoría quedan registrados automáticamente usando el paquete `owen-it/laravel-auditing`.
- Puedes consultarlos en la base de datos en la tabla `audits`.
- Para revisar acciones en código o API, puedes usar Laravel Telescope para monitorear las solicitudes que generan auditorías.

¡Listo! Con esto tienes la API funcional, documentada y monitoreada. Cualquier duda o mejora, ¡estoy atento!
