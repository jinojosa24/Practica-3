# Practica-3

## Realiza unha consulta "dig danielcastelao.org" e identific cada parte da resposta (IN, CNAME, A, QUERY SECTION, ANSWER SECTION, AUTHORITY SECTION, etc)
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
 En esta consulta aparece vacia, deberia de indicar los servidores que se encuentran asociados a dicho dominio.

## Realiza consutas dos seguintes nomes e identifica as diferencias: moodle.danielcastelao.org, www.danielcastelao.org  
Las diferencias muestran que **moodle** no está configurado, mientras que el dominio www.danielcastelao.org sí está activo.
### Diferencia:
En el estado de `moodle` dice: NXDOMAIN mientras que el de `danielcastelao` dice : NOERROR. Esto quiere decir que el `moodle` no tiene un dominio o una  direccion IP mientras que la `danielcastelao` Si tiene un dominio y una direccion IP.
## Averigua o nome e IP dos servidores de DNS autoritativos de www.danielcastelao.org, por qué soen ser 2 servidores autoritativos?

## Realiza as consultas de nomes inversas: 130.206.164.68 e de outras dúas IPs que se che ocorran.

## A qué servidor DNS estás consultando? Cómo o podes cambiar sen tocar os ficheiros de configuración do sistema?

## Obtén o rexistro SOA (Start of Authority) do dominio  moodle.danielcastelao.org preguntándolle ó servidor DNS de google e logo preoguntándollo directamente ó servidor primario do dominio danielcastelao.org. 

## Consulta a IP de www.elpais.com. Cánto tempo queda almaceado o rexistro de recurso no DNS local?, se preguntas ó DNS local por este recurso, qué observas no TTL do rexistro?

## Busca o TTL de distintos nomes de dominio de servicios que escollas, a qué se poden deber as diferencias?

## Determina o TTL máximo (original) dun nome de dominio.
    
## Averigua cántas máquinas con distintas IPs están detrás do dominio web www.google.es, sempre son as mesmas e na mesma orde? por qué?

## Pregunta o mesmo a un server raiz (J.ROOTSERVERS.NET por exemplo) e comproba na resposta se o server acepta o modo recursivo

## Se queremos ver tóda-las queries que fai o servidor de DNS, qué opción temos que usar? averigua a IP de www.timesonline.co.uk, especifica os pasos dados

## Usando a información dispoñible a traveso do DNS especifica a máquina (nome e IP) ou máquinas que actúan como servers de correo do dominio danielcastelao.org

## Podes obter os rexistros AAAA de www.facebook.com? a qué corresponden?
