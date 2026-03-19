# Preguntas de Comprension‌‌‌​‌​‌‌​﻿‍‍​﻿‍​‌‍​‌​﻿‌‌​﻿​‌​﻿‌‌​﻿‌‌​﻿‍​​﻿​​​﻿‌‌​﻿​‌‌‍​‍‌‍‌‌​﻿​﻿​﻿​​​﻿​﻿​﻿‍​

Responder con sus propias palabras.

---

## 1. Infraestructura
**Si tu app necesita conectarse a PostgreSQL pero el contenedor de la BD tarda 30 segundos en arrancar, que pasa? Como lo solucionarias?**

El problema es de timing → se soluciona haciendo que la app espere o reintente hasta que la BD esté lista.

## 2. JPA
**Por que `findAll()` puede ser lento con 100,000 registros? Que alternativa usarias?**

FindAll() es lento porque carga todo → mejor usar paginación o consultas parciales.

## 3. API REST
**Diferencia entre error 400 y error 500. Un ejemplo de cada uno en tu proyecto.**

-400 → error del cliente (datos incorrectos)

{
"titulo": "",
"autor": "Cervantes"
}

titulo vacío → falla validación (@NotBlank)
➡ Devuelve 400

-500 → error del servidor (fallo interno)

GET /api/libros

La BD está caída o mal configurada
➡ Spring lanza excepción → 500

## 4. Escalabilidad
**Si tu app pasa de 100 a 10,000 usuarios, que cambiarias en Docker?**

Pasas de un entorno simple a uno escalable y distribuido:
Más instancias + balanceo + mejor BD + control de recursos.
