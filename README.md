# MySQL + phpMyAdmin Docker Setup

Configuración de MySQL con phpMyAdmin usando docker compose.

## Servicios

- **MySQL 8.0**: Base de datos
- **phpMyAdmin 5.2.2**: Interfaz web

## Configuración

Crea una copia de env-example y renómbrala a `.env`:

## Uso

### Iniciar los servicios
```bash
docker compose up -d
```

### Detener los servicios
```bash
docker compose down
```

### Ver logs
```bash
docker compose logs
docker compose logs mysql
docker compose logs phpmyadmin
```

## Estructura del proyecto

```
.
├── docker-compose.yaml  # Configuración de servicios
├── Dockerfile          # Imagen personalizada de MySQL
└── README.md           # Documentación
```

## Comandos útiles

```bash
# Reiniciar solo un servicio
docker compose restart mysql
docker compose restart phpmyadmin

# Ver estado de los contenedores
docker compose ps

# Acceder al contenedor MySQL
docker compose exec mysql bash

# Backup de la base de datos
docker compose exec mysql mysqldump -u nombre_usuario -p nombre_base_dato > backup.sql

# Restaurar backup
docker compose exec -i mysql mysql -u nombre_usuario -p nombre_base_dato < backup.sql
```
