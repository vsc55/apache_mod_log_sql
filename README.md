# Modulo de apache para guardar logs directamente en bases de datos (mod_log_sql)

## Autores
### Código base del mod_log_sql: 
- OutOfOrder.cc (http://www.outoforder.cc/projects/apache/mod_log_sql/)

### Parche para soportar X-Forwarded-For y mod_vhs HTTP header:
- Parche inicial sobre la versión 1.100 de mod_log_sql:
  - Rene Kanzler (http://lists.outoforder.cc/pipermail/mod_log_sql/2009-June/000333.html)
- Actualización de del parche a la versión 1.101:
  - Javier Pastor



## Nuevas funciones
- X-Forwarded-For
  - Se ha añadido soporte para registrar las direcciones IP reales de los clientes cuando apache está ta detrás de un proxy. El nuevo carácter para la cadena de formato de registro es `x`.


## Modo de uso
- X-Fordered-For
  - Para registrar direcciones IP reales detrás de un proxy, reemplace "h" con "x" en su cadena de formato de registro.
  > Si no se encuentra el encabezado HTTP X-Fordered-For, se registrará la dirección IP remota.


- Mod_vhs
  - Los usuarios de mod_vhs deben reemplazar "v" o "V" con "g" de acuerdo con el manual en http://openvisp.fr/doku/doku.php?id=mod_vhs:logs
  > Si no se encuentra el encabezado HTTP mod_vhs, se registrará el nombre de host virtual.
  