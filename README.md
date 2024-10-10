# Practica-3

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

Utilizando este comando `dig @8.8.8.8 www.facebook.com` consultariamos facebook con el ser de google 8.8.8.8


## 6. Obtén o rexistro SOA (Start of Authority) do dominio  moodle.danielcastelao.org preguntándolle ó servidor DNS de google e logo preoguntándollo directamente ó servidor primario do dominio danielcastelao.org. 

## 7. Consulta a IP de www.elpais.com. Cánto tempo queda almaceado o rexistro de recurso no DNS local?, se preguntas ó DNS local por este recurso, qué observas no TTL do rexistro?

## 8. Busca o TTL de distintos nomes de dominio de servicios que escollas, a qué se poden deber as diferencias?

## 9. Determina o TTL máximo (original) dun nome de dominio.
    
## 10. Averigua cántas máquinas con distintas IPs están detrás do dominio web www.google.es, sempre son as mesmas e na mesma orde? por qué?

## 11. Pregunta o mesmo a un server raiz (J.ROOTSERVERS.NET por exemplo) e comproba na resposta se o server acepta o modo recursivo

## 12. Se queremos ver tóda-las queries que fai o servidor de DNS, qué opción temos que usar? averigua a IP de www.timesonline.co.uk, especifica os pasos dados

## 13. Usando a información dispoñible a traveso do DNS especifica a máquina (nome e IP) ou máquinas que actúan como servers de correo do dominio danielcastelao.org

## 14. Podes obter os rexistros AAAA de www.facebook.com? a qué corresponden?
