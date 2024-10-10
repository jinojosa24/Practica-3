<div style="background-color: lightblue; padding: 10px;">

# Practica-3 DIG
</div>
## 1. Realiza unha consulta "dig danielcastelao.org" e identific cada parte da resposta (IN, CNAME, A, QUERY SECTION, ANSWER SECTION, AUTHORITY SECTION, etc)

 Al realiza la consulta utilizando el comando `dig danielcastelao.org` nos da un informacion detallada sobre:
 ### IN: 
 Es un resgistro de INTERNET
 ### A: 
 Nombre de dominio
 ### QUERY SECTION: 
 Muestra la consulta realizada, en este caso la consulta se esta realizando en el dominio danielcastelao.
 ### ANSAWER SECTION: 
 Muestra la direccion IP asociada al dominio (178.211.133.37)
 ### AUTHORITY SECTION:
 En esta consulta aparece vacia, deberia de indicar los servidores autoritativos que se encuentran asociados a dicho dominio.

## 2. Realiza consutas dos seguintes nomes e identifica as diferencias: moodle.danielcastelao.org, www.danielcastelao.org  

Las diferencias muestran que **moodle** no está configurado, mientras que el dominio www.danielcastelao.org sí está activo.

### Diferencia:

En el estado de `moodle` dice: NXDOMAIN mientras que el de `danielcastelao` dice : NOERROR. Esto quiere decir que el `moodle` no tiene un dominio o una  direccion IP mientras que la `danielcastelao` Si tiene un dominio y una direccion IP.

## 3. Averigua o nome e IP dos servidores de DNS autoritativos de www.danielcastelao.org, por qué soen ser 2 servidores autoritativos?

Utilizando el comando `dig NS www.danielcastelao.org` en la terminal nos dara la informacion de los 2 servidores autoritativos en este caso son *ns1.hover.com* que se encarga de los nombres para el dominio `danielcastelao.org` *dnsmaster.hover.com* es el que se encarag de los correos de administracion del DNS. suelen ser dos servidores o mas por si uno falla el otro se encuentre disponible, redundancia, diponibilidad geografica, mejor accesibilidad. 

Ahora para averiguar la direccion IP se utiliza el comando `dig A dnsmaster.hover.com` y la direccion IP es 216.40.34.41  y la del servidor `ns1.hover.com` es 216.40.47.26.

## 4. Realiza as consultas de nomes inversas: 130.206.164.68 e de outras dúas IPs que se che ocorran.

Realizamos el comando `dig 130.206.164.68` tambien se podria utilizar el comando `dig -x 130.206.164.68` y asi nos simplifica el resultado.
`dig 8.8.8.8`

## 5. A qué servidor DNS estás consultando? Cómo o podes cambiar sen tocar os ficheiros de configuración do sistema?

Este en el servidor que estoy consultando al lanzar el comando `dig`en la terminal me da este resultado. *;; SERVER: 127.0.0.53#53(127.0.0.53) (UDP)* 

Utilizando este comando `dig @8.8.8.8 www.facebook.com` consultariamos facebook con el server de google 8.8.8.8

## 6. Obtén o rexistro SOA (Start of Authority) do dominio  moodle.danielcastelao.org preguntándolle ó servidor DNS de google e logo preoguntándollo directamente ó servidor primario do dominio danielcastelao.org. 

Para consultarlo en la terminal con el comando `dig @8.8.8.8 SOA moodle.danielcastelao.org` y se obtendra la informacion del registro SOA.

Ahora para consultarlo con el servidor primario del dominio danielcastelao.org utilizando el comando `dig @ns1.hover.com SOA moodle.danielcastelao.org` nos dara la informacion del registro SOA.

## 7. Consulta a IP de www.elpais.com. Cánto tempo queda almaceado o rexistro de recurso no DNS local?, se preguntas ó DNS local por este recurso, qué observas no TTL do rexistro?

 Con el comando `dig www.elpais.com` La IP de www.elpais.com tiene un TTL de 3 segundos, el registro se guarda en la caché del DNS local solo durante ese tiempo. y en la CNAME	prisa-us-eu.map.fastly.net. 

## 8. Busca o TTL de distintos nomes de dominio de servicios que escollas, a qué se poden deber as diferencias?
Estos fueron las dos dominios que busque `dig www.google.com` y `dig www.microsoft.com`  la cual arrojo, google un TTL de *245* y la de microsoft  *2742*.

El TTL pricipalmente se debe a la necesita de la empresa de mantener un servicio estable y rapido. 


## 9. Determina o TTL máximo (original) dun nome de dominio.

El TTL es 2021 segundos.
*;; ANSWER SECTION:*
*www.microsoft.		2021	IN	A	20.112.250.133*

## 10. Averigua cántas máquinas con distintas IPs están detrás do dominio web www.google.es, sempre son as mesmas e na mesma orde? por qué?
Luego de hacer la  varias veces la consulta, siempre dio el mismo direccionamiento IP *142.250.184.163* lo que fue variando fue la TTL disminuyendo. 
En algunos casos la IP podria variar dependera del dominio que se consulte.
## 11. Pregunta o mesmo a un server raiz (J.ROOTSERVERS.NET por exemplo) e comproba na resposta se o server acepta o modo recursivo.

Luego de hacer la consulta el server no acepta respuesta recursiva. 
`;; WARNING: recursion requested but not available`

## 12. Se queremos ver tóda-las queries que fai o servidor de DNS, qué opción temos que usar? averigua a IP de www.timesonline.co.uk, especifica os pasos dados

Para averiguar la direccion IP de www.timesonline.co.uk se realiza la siguiente consulta en la terminal `dig www.timeonline.co.uk SOA` nos da el server autoritativo y luego consultamos la IP mediante su server autoritativo `dig @ns-1826.awsdns-36.co.uk www.timesonline.co.uk` y la direccion IP es *SERVER: 205.251.199.34* 

## 13. Usando a información dispoñible a traveso do DNS especifica a máquina (nome e IP) ou máquinas que actúan como servers de correo do dominio danielcastelao.org
utilizando el comando `dig danielcastelao.org mx` Los servers de correo de dominio de `danielcastelao.org`son los siguientes:

spmx4.googlemail.com.    IP 142.250.150.27
aspmx5.googlemail.com.   IP 142.251.168.27
alt2.aspmx.l.google.com. IP 142.251.9.27
alt1.aspmx.l.google.com. IP 142.250.153.26
aspmx2.googlemail.com.   IP 142.250.153.27
aspmx3.googlemail.com.   IP 142.251.9.26
aspmx.l.google.com.      IP 74.125.71.26

Para saber la IP de cada uno de estos con el comando `dig a` seguido del nombre.

## 14. Podes obter os rexistros AAAA de www.facebook.com? a qué corresponden?
Luego de hacer la consulta, los registros `AAAA`corresponden al direccionamiento IPv6. *star-mini.c10r.facebook.com. 6	IN	AAAA	2a03:2880:f104:83:face:b00c:0:25de* informacion del registro.

