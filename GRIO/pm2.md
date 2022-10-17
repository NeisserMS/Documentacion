## ¿Qué es PM2?
Es un gestor de procesos en producción para las aplicaciones Nodejs y permite mantener siempre activas las aplicaciones y volver a cargarlas evitando los tiempos de inactividad. 

### Caracteristicas:
- Capacidad de manejar un montón de aplicaciones (ver sus estados).
- Capacidad de minitoreo de memoria y cps de los procesos.
- Manejo de logs.
- Balanceo de carga.
- Iniciar las aplicaciones una vez el servidor se inicie.
- Capacidad de "mirar tu código" si es que este cambia.

### Pre requisito:
- Tener instalado Nodejs

### Comandos:
Instalar:
```bash
   npm install -g pm2
```
Iniciar: (nombre del proceso, id del proceso o para todos "all")
```bash
   pm2 start example.js
```
Reiniciar:
```bash
   pm2 restart
```
Detener:
```bash
   pm2 stop example.js
```
Asignar un alias para un mejor manejo:
```bash
   pm2 start example.js --name "mi-bot"
```
Obtener lista de los procesos actuales con sus nombres e ids:
```bash
   pm2 list
```
Para obtener una información mas detallada y actualizada en tiempo real:
```bash
   pm2 monit
```
Mostrar los últimos logs (muestra los nuevos mensajes de los procesos por salida en consola).
```bash
   pm2 log
```
Eliminar todos los logs:
```bash
   pm2 flush
```
Ver estado del proceso:
```bash
   pm2 show example.js
```
Eliminar:
```bash
   pm2 delete example.js
```

Configurar el Script de startup del servidor:
Con los procesos ya en marcha mediante pm2 podemos automatizar el proceso mediante un script. Cada vez que reiniciemos el servidor seguirán ejecutandose sin tener que hacerlo manualmente para reactivarlos ya que pm2 está diseñado para funcionar como una configuración predeterminada dentro del sistema linux, así que este script actuará como un servicioque se puede reiniciar al iniciar el sistema.

```bash
   pm2 startup
```
Para confirmar que se ejecuta bajo sistema:
```bash
   systemctl status example.js o example.service
```
Para levantar **todos** los servicios o procesos:
```bash
   pm2 resurrect
```
Guardar el proceso de iniciar con un reinicio del sistema:
```bash
   pm2 save
```
Actualizar PM2:
```bash
   pm2 update
```
Desinstalar:

```bash
   pm2 unstartup systemd
```

#### Referencias:
https://tecnonucleous.com/2018/03/28/usar-pm2-para-mantener-el-bot-de-telegram-encendido/#:~:text=Pm2%20es%20un%20gestor%20de,comunes%20de%20administrador%20del%20sistema.
https://www.juanonlab.com/blog/es/uso-de-pm2
https://help.clouding.io/hc/es/articles/4402736917394-C%C3%B3mo-usar-PM2-para-gestionar-una-app-en-Node-js-
https://muylinux.xyz/a-continuacion-se-explica-como-habilitar-pm2-para-que-inicie-la-aplicacion-node-js-automaticamente-al-iniciar-el-sistema/