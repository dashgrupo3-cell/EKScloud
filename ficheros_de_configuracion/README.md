# ORDEN DE EJECUCIÓN DE LOS FICHEROS

Primero de todo ejecutamos el fichero llamado “secret-app.yml” usamos el comando 

```
kubectl apply -f secret-app.yml
```

Esto lo que hace es crearnos una contraseña para el mysql que usamos posteriormente en el resto de ficheros. Es importante destacar que este contraseña no esta en texto plano sino que esta encriptada en base 64, con lo cual si queremos cambiar la contraseña deberiamos primero encriptarla en base 64



Como segundo fichero que tenemos que ejecutar es el “pv-pvc.yml”
```
kubectl apply -f pv-pvc.yml 
```
Este comando lo que hace es crear 2 volúmenes. Para entenderlo mejor con 2 discos duros de 10 gigas de almacenamiento EBS uno para el MYSQL y otro para el Wordpress 



Como tercer comando a ejecutar tenemos que ejecutar el fichero “mysql-deployment.yml”
```
kubectl apply -f mysql-deployment.yml
```
Con este comando lanzamos la base de datos en MYSQL y lo que nos hace es crear el POD con un MYSQL dentro el cual se usa como base da datos oara el wordpress



Por último ejecutamos el wordpress con el comando 
```
kubectl apply -f wordpress-deployment.yml
```
Y este último comando nos acaba de lanzar un POD con el wordpress dentro, al cual nos conectaremos posteriormente con el balanceador de cargas  
