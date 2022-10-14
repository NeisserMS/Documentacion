Termius: herramienta para gestionar servidores.

Para listar tus proyectos dentro del servidor:
```bash
pm2 list
```
Para ver tus directorios: ls
```bash
ls
```
Para visualizar los detalles de los archivos : 
```bash
ll
```

Para DevOps tenemos que integrarnos al servidor para poder desplegar.
Para conectarnos con azure tendrá que ser con **SSH**

Entrar al server:
```bash
cd gruporomero-server/
```

Jalar los cambios desde la rama developer:
```bash
git pull origin develop
```
Importante: Te pedirá una clave!


Actualizar los pquetes  o descargarlos dentro del server: 
```bash
npm i
```

Hacer el restart por nombre del proyecto:
```bash
pm2 restart gruporomero-server
```
Suponiendo de que hay conflictos porque alguuien ha subido cambios manualmente y no puedes bajar cambios.

Todos mis cambios que tengo los desaparezco, pero no lo borro:
```bash
git stash
```
Para retornar tus cambios que tenias:
```bash
git stash apply
```
INFO:
crud-server: API de la web
server: API de la app movil
crud-web: API de la web

Para ver los archivos detallado de tu proyecto:
```bash
pm2 info gruporomero-crud-web
```
 
Ejecutar dentro de la carpeta del proyecto crud-web:
```bash
run start:prod o start:prod
```

Despues de levantarlo, compilarlo:
```bash
npm run build
```
Después hacerle un restart.


Para meter el proyecto dentro de pm2 (solo una vez):
```bash
pm2 start --name gruporomero-crud-web npm -- run start:prod
```

¿Qué pasa si el servidor se apaga y se prende?
Como no les dan permiso para agregar comandas adicionales para apagado, prendido o reinicio o por si no existe.
Ejecutar: 

```bash
pm2 resurrect
```
Para validar si el servidor está prendido o apagado: 
```bash
pm2 list | grep "gruporomero-server"
```
Si aparece es que está prendido, y sino solo ejecutar:
```bash
pm2 restart gruporomero-server
```

Ver los errores:
```bash
pm2 log gruporomero-server
```





