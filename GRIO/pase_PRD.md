## GRIO

### VERIFICADO
1. Stage PRD verificado y actualizado.
2. Actualizado el instrumentation key para PRD en el grupo de libreria
3. Grupo de variables actualizado
4. ENV de para PRD ya está creado.
5. El nombre del crud-server en PRD es gruporomero-crud-server en ambos servidores
6. Las conexiones para PRD a AWS ya existe.
7. Los tres proyectos están con la versión 14.17.5 de Nodejs
8. Politicas de las ramas actualizadas en los tres proyectos
9. Ramas homologadas en los tres proyectos
10. Variables de entorno en la web de prd son iguales con los del grupo de libreria.


### PENDIENTES
1. Agregar el key del App Insgiht de PRD
   
### PASE A PRD
1. Ejecutar los pipelines desde la rama main

### Comandos para levantar los proyectos:
Para web: 
```bash
    pm2 start --name gruporomero-crud-web npm  -- run start:prod
```

para Backend
```bash
    pm2 start --name gruporomero-server index.js
```