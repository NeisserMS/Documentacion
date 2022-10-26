### ECS: AMAZON ELASTIC CONTAINER SERVICE

Orquestador: Son servicios para implementar, programar, escalar y administrar aplicaciones en contenedores. existe dos servicios principales ECS y Amazon
Elastic Kubernetes Service.

Hospedaje: Aquí es donde se ejecutan los contenedores.  Como ejemplo: Amazon EC2 (servicio de maquinas virtuales: linux y windows) y AWS Fargate (para correr y ejecutar contenedores de manera **serveles** sin preocuparnos por la adm, parchados y gestion de las maquinas virtuales).

Registro de imágenes: Repositorios de imagenes del contenedor, como Amazon Elastic Container Registry (para almacenar las imagenes, versionar y compartir).


#### ¿Qué es ECS?
Es un servicio gestionado por AWS que se encarga de hacer la orquestación y concste en dos principales tareas:
1. Administrar los clusters: Administra nuestras maquinas virtuales o servicios de de Fargate.
2. Mecanismo de colocación: distribuye la carga de forma eficiente , osea los contenedores a través de una flota de maquinas virtuales o servicios Fargate
   . De esta manera vamos a escalar de un contenedor a cientos de miles de contenedores en simultaneo, pudiendo ajustarnos a la carga o a las reglas de negocio que nosotros definamos para poder hacer un escalado tanto vertical como horizontal en las capacidades de nuestros contenedores. 

##### ¿Qué es un contenedor?
Dentro del cluster podemos tener varios contenedores de diferentes tipos, pueden ser distintos microservicios, distintas piezas
de nuestras aplicaciones y cada uno puede tener diferentes caractetisticas de computo, diferentes metodos de almacenamiento, etc.

##### ¿Qué es un Task?
Dentro de un cluster para ejecutar los contenedores tenemos que basarnos en las definiciones que se hicieron previamente. La tarea es una ejecuón en tiempo
de uno de estos contenedores que previamente definimos. Podemos tener diversas tareas del mismo tipo y a su bez una tarea o una definición se puede componer
de un conjunto de contenedores, por ejemplo yo en una tarea puedo tener dos contenedores ejecutandose al mismo tiempo.
![Task](/img/task.png)
Un caso tipico de esto es cuando tenemos un contenedor de tipo Sidecar que es basicamente un concepto que se utiliza para definir a contenedores que acompaña al contenedor principal y le da funcionalidades extras, como por ejemplo de login, monitoreo, conectividad. Entonces una tarea puede ser un contenedor o una colección (conjunto) de contenedores.

##### ¿Qué es un Servicio?
¿Qué sucede cuando queremos crear multiples tareas identicas?, osea queremos que estás se escalen de forma automatica en base a CPU, memoria, etc.
Es un conjunto de tareas que nos permite definir unas reglas para hacer un escalado de forma horizontal y luego podemos exponer nuestro servicio y conectarlo con un servicio de AWS Elatic Balance que es un servicio para el balance ode cargas HTTPS o HTTP. De esta manera logramos exponer de forma muy sencilla nuestra app a internet o incluso hacerlo de forma privada.

##### AWS FARGATE:
No tenemos la necesidad de administrar una maquina virtual. Este se concentra en lo que realmente aporta valor al negocio, solo ejecutamos contenedores serveles, puede ser 10, 20, 200, simplemente vamos a decirle el tamaño, la cantidad de CPU, IPS, si va a conectarse a un balenceador, que tipo de SO operativo tendrá, etc.

##### Simplicidad de ECS:
- La forma opinionada de AWS de ejecutar contenedores a escala.
- Reducir las decisiones sin sacrificar la escalabilidad y seguridad.
- Disminuya el tiempo para crear, implementar y migrar aplicaciones, osea simplicar esa exp al máximo.


  
Repositorio de imagenes publicas:
```bash
   https://gallery.ecr.aws/
```

Crear un Cluster:
```bash
   https://linuxhint.com/create-ecs-cluster-aws/
```













