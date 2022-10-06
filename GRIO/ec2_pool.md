### Creación de un agent pool y conexión

Nota: Si no eres usuario root agregar **sudo** en algunos comandos.

1. Conectarte a la máquina virtual creada en el EC2
   ![ec2](img/ec2.png)

2. Crear una carpeta para tu agente:
```bash
    mkdir /myagent2
```
2. Moverme a la carpeta creada:
```bash
    cd /myagent2/
```
3. Retroceder a una carpeta raiz
```bash
    cd ..
```
4. Darle los permisos a myagent2
```bash
    chmod -R 777 myagent2
```
5. Descargar el agente
```bash
    wget https://vstsagentpackage.azureedge.net/agent/2.210.1/vsts-agent-win-x64-2.210.1.zip
``` 
![Descargar](img/descargar.png)
6.  Ejecutar el archivo del agente:
```bash
    sudo tar zxvf vsts-agent-linux-x64-2.210.1.tar.gz
``` 
7. Ejecutar el agente:
```bash
    ./config.sh
``` 
8. Enter server URL:
```bash
    https://dev.azure.com/gr-grio/
``` 
9. Access Tokken:
```bash
    ***************************
```
10. Inciar el agente en linux:
```bash
    ./run.sh
```

#### ERRORES ENCONTRADOS

Copiar un archivo de windows a linux:
```bash
    scp -i GRMROPCBD02.pem D:/archivos_grio/libssl1.0.0_1.0.2n-1ubuntu5.10_amd64.deb ubuntu@ec2-3-90-36-252.compute-1.amazonaws.com:/myagent
```
**No usable version of libssl was found**
links: Descargar el archivo, pero debe ser acorde a su arquitectura.
https://forum.unity.com/threads/workaround-for-libssl-issue-on-ubuntu-22-04.1271405/
http://security.ubuntu.com/ubuntu/pool/main/o/openssl1.0/

Después ejecutar:
```bash
    sudo dpkg -i libssl1.0.0_1.0.2n-1ubuntu5.10_amd64.deb
```

posiblemente de un nuevo error:
 **The SSL connection could not be established, see inner exception**. Ejecutar:
```bash
    export AZP_AGENT_USE_LEGACY_HTTP=true
```