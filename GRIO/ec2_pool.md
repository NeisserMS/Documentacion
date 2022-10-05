### Crear la conexión 

1. Crear una carpeta para t uagente:
```bash
    sudo mkdir /myagent2
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
    sudo chmod -R 777 myagent2
```
5. 
```bash
    sudo wget https://vstsagentpackage.azure.net
``` 
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
**No usable version of libssl was found**
links: Descargar el archivo, pero debe ser acorde a su arquitectura.
https://forum.unity.com/threads/workaround-for-libssl-issue-on-ubuntu-22-04.1271405/
http://security.ubuntu.com/ubuntu/pool/main/o/openssl1.0/

Después ejecutar:
```bash
    sudo dpkg -i libssl1.0.0_1.0.2n-1ubuntu5.10_amd64.deb
```

posiblemente de un nuevo error **The SSL connection could not be established, see inner exception**. Ejecutar:
```bash
    export AZP_AGENT_USE_LEGACY_HTTP=tru
```