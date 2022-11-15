# Oracle Cloud videos


## Oracle Cloud
* Instances
* VCN
* VestaCP
* FTP

## Youtube Resources https://www.youtube.com/playlist?list=PLUhIV-TEo8VZD6en-zm-j762QpepY61Mk
* 1.- instalando putty y puttygen
* 2.- Generar llave publica y privada
* 3.- Oracle Cloud, accediendo por primera vez desde tu correo
* 4.- Oracle Cloud Creando maquina Virtual 1-2
* 5.- Oracle Cloud Creando maquina Virtual 2-2
* 5A.- conexion putty a maquina virtual
* 6.- Instalando VESTA en la maquina virtual 1-3
* 7.- Instalando VESTA en la maquina virtual 2-3
* 8.- Instalando VESTA en la maquina virtual 3-3
* 8-A .- Maquina Virtual Seguridad en VESTA
* 9.- Maquina Virtual puerto 80 y 8083
* 9A.- Maquina Virtual VESTA Configurando usuario FTP
* 10.- Instalando y configurar Sublime Text FTP 1-2
* 11.- Instalando y configurar Sublime Text FTP 2-2
* 12.- Confirmando que funcione Sublime y FTP





## Pasos para instalar Java en ubuntu
```
sudo apt install default-jre            
sudo apt install openjdk-11-jre-headless
sudo apt install openjdk-8-jre-headless

sudo apt install default-jdk            
sudo apt install openjdk-11-jdk-headless
sudo apt install ecj                    
sudo apt install openjdk-8-jdk-headless

ubuntu@129:~$ java --version
openjdk 11.0.7 2020-04-14
OpenJDK Runtime Environment (build 11.0.7+10-post-Ubuntu-2ubuntu218.04)
OpenJDK 64-Bit Server VM (build 11.0.7+10-post-Ubuntu-2ubuntu218.04, mixed mode, sharing)

/usr/lib/jvm/java-8-openjdk-amd64/jre/

/usr/lib/jvm/java-11-openjdk-amd64/

```

## HTTPS

```
sudo rm /usr/local/vesta/ssl/*
sudo ln -s /home/admin/conf/web/ssl.luisreylara.ml.key /usr/local/vesta/ssl/certificate.key
sudo ln -s /home/admin/conf/web/ssl.luisreylara.ml.crt /usr/local/vesta/ssl/certificate.crt
sudo ln -s /home/admin/conf/web/ssl.luisreylara.ml.crt /etc/emqx/certs/cert.pem
sudo service vesta restart
```

## root on mysql
```
sudo nano /usr/local/vesta/conf/mysql.conf
sudo cat /usr/local/vesta/conf/mysql.conf
mysql -h localhost -u root -p


reate database prueba;
GRANT ALL PRIVILEGES ON prueba.* TO 'admin_default'@'%';
FLUSH PRIVILEGES;

CREATE USER ‘usuario’@‘localhost' IDENTIFIED BY 'tu_contrasena';
CREATE USER ‘usuario’@‘%’ IDENTIFIED BY ‘upjr2021;
create database lector;
GRANT ALL PRIVILEGES ON lector.* TO ‘usuario’@‘%’;

ALTER USER 'root'@'localhost' IDENTIFIED BY 'MyNewPass';

```

## WHERE IS JAVA
```
whereis java
ls -l /usr/bin/java
ls -l /etc/alternatives/java/
/usr/lib/jvm/java-11-openjdk-amd64/

```


## Cómo restablecer la contraseña de root de MySQL en Ubuntu
```
sudo service mysql stop
sudo mkdir -p /var/run/mysqld
sudo chown mysql:mysql /var/run/mysqld
sudo /usr/sbin/mysqld --skip-grant-tables --skip-networking &
mysql -u root
mysql> FLUSH PRIVILEGES;
mysql> USE mysql;
mysql> UPDATE user SET authentication_string=PASSWORD("hola2018") WHERE User='root';
mysql> UPDATE user SET plugin="mysql_native_password" WHERE User='root';
mysql> quit
sudo pkill mysqld
sudo service mysql start
```

