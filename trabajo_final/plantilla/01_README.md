# Trabajo Final — Javier Fdez‌‌‌​‌​‌‌​﻿‍‍‌‍​‍​﻿​﻿​﻿​‍​﻿‌‌‌‍‌​‌‍​‍‌‍‌‍‌‍​‌​﻿‌‌​﻿‍‌‌‍​‌‌‍​‌​﻿​‍‌‍‌​​﻿‍‌‌‍‌‌

## Blueprint elegido
Biblioteca

## Descripcion
Se ha desarrollado una API REST con Spring Boot para gestionar una biblioteca, 
permitiendo administrar libros, autores, ejemplares, socios y préstamos. 
El sistema digitaliza el control de préstamos y aplica reglas como disponibilidad 
de ejemplares y penalizaciones por retrasos.

## Entidades
Entidades:
- LibroConceptual (ISBN, título, año, género)
- Autor (id, nombre, país)
- EjemplarLibro (id, código, estado, prestado)
- SocioLector (id, dni, nombre, penalizado)
- PrestamoActivo (id, fechas de préstamo y devolución)

Relaciones:
- ManyToMany: Autor ↔ Libro
- ManyToOne: Ejemplar → Libro
- ManyToOne: Préstamo → Socio y Ejemplar

Enum:
- EstadoEjemplar con almacenamiento como texto

## Endpoints de la API


| Verbo  | URL                        | Descripción                         |
| ------ | -------------------------- | ----------------------------------- |
| GET    | `/autores`                 | Listar todos los autores            |
| POST   | `/autores`                 | Crear un nuevo autor                |
| GET    | `/libros`                  | Listar todos los libros             |
| GET    | `/libros/{isbn}`           | Obtener un libro por ISBN           |
| POST   | `/libros`                  | Crear un nuevo libro                |
| PUT    | `/libros/{isbn}`           | Actualizar un libro existente       |
| DELETE | `/libros/{isbn}`           | Eliminar un libro                   |
| GET    | `/libros/genero/{genero}`  | Buscar libros por género            |
| GET    | `/ejemplares/disponibles`  | Listar ejemplares disponibles       |
| POST   | `/ejemplares`              | Crear un nuevo ejemplar             |
| GET    | `/socios/dni/{dni}`        | Buscar socio por DNI                |
| POST   | `/socios`                  | Crear un nuevo socio                |
| GET    | `/prestamos`               | Listar todos los préstamos          |
| GET    | `/prestamos/socio/{id}`    | Listar préstamos de un socio        |
| POST   | `/prestamos`               | Crear un préstamo                   |
| PUT    | `/prestamos/devolver/{id}` | Devolver un libro (cerrar préstamo) |


## Como ejecutar

```bash
# Con Docker
docker compose up -d

# Sin Docker (H2)
mvn spring-boot:run
```
