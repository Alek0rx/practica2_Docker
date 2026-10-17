# Limitar uso de procesador
Limitar la cantidad de núcleos de CPU:
```
--cpus=<número de núcleos>
```

Asignar núcleos de CPU específicos:
```
--cpuset-cpus=<lista de núcleos>
```

**¿Como saber el número de procesadores virtuales que tiene una máquina?**
Existen varias formas de conocer el número de procesadores virtuales presentes en una máquina:
* Accediendo al administrador de tareas, en la sección de rendimiento se puede visualizar el número de procesadores lógicos.
* Otra forma es investigando en internet las especificaciones del procesador de la máquina.
* Ingresando el siguiente comando en CMD/PowerShell:
```
wmic cpu get NumberOfLogicalProcessors
```

## Ejemplos
_Puedes copiar y ejecutar directamente cada uno de los comandos_

Limitar el uso de CPU a 1.5 núcleos
```
docker run -d --name server-nginx --cpus="1.5" nginx:alpine
```

Restringir el contenedor para que use los núcleos de CPU 0 a 2:
```
docker run -d --name server-nginx --cpuset-cpus="0-2" nginx:alpine
```

Restringir el contenedor para que use los núcleos de CPU 1 y 3:
```
docker run -d --name server-nginx --cpuset-cpus="1,3" nginx:alpine
```
