# Protocolos IPv4 e IPv6


## **1. Introducción**

El protocolo de Internet versión cuatro (IPv4) del protocolo IP y el primero que se implementó a gran escala. Dicho protocolo está definido en el RFC (Request for coments) 791. IPv4 usa direcciones de 32 bits, cuenta con un espacio de 4.294.967.296 direcciones únicas, parece que tuviera muchas, pero no todas pueden ser ocupadas. Existen varios factores que han provocado que de a poco se vayan minimizando estas direcciones. 

IPv4 inicialmente fue creado como un experimento en el cual se creía que 4300 millones de direcciones eran suficientes para abastecer el gran mercado que iba a abarcar, no se pensaba que se iban a ocupar este gran número de direcciones en tan poco tiempo y mucho menos la desenfrenada creación de nuevos equipos o dispositivos que iban a utilizar direcciones IP.

El exponencial crecimiento de usuarios en Internet causó el agotamiento de direcciones IPv4, la cual fue la pauta para la creación de IPv6, quien se espera sea implementando en todas las redes de datos a nivel mundial.  Por esto es muy importante conocer las características de IPv6, pero principalmente saber el funcionamiento del enrutamiento estático y dinámico, diseñando topologías para realizar pruebas con los protocolos de enrutamiento: RIPng, EIGRP, OSPFv3 e   IS-IS; comparándolos entre los del mismo tipo, vector distancia y estado de enlace, para así reconocer sus ventajas y desventajas entre sí.

## **2. Desarrollo** 

### **2.1	Agotamiento de las direcciones IPv4 y las medidas paliativas.**

Agotamiento IPv4 se refiere a una etapa de reservas donde se restringen en tamaño y periodicidad las asignaciones. Por tanto, ya no existen suficientes direcciones para cubrir el direccionamiento IPv4. 

Para el área de Latinoamérica y el Caribe el espacio de direcciones IP es distribuido por IANA a LACNIC, para ser a su vez distribuidos y asignados a Registros Nacionales de Internet (NIRs), Proveedores de Servicios de Internet (ISP) y usuarios finales. La organización lleva entregadas más de 182 millones de direcciones IPv4 en América Latina y el Caribe desde el inicio de sus operaciones en 2002.

Para poder organizar toda la asignación de direcciones a nivel global se hace uso de la distribución de espacio de los recursos de numeración siguiendo un esquema jerárquico, como se muestra en la siguiente figura.

![1](/Dispositivos_de_Transmisión/1.png) 

Los Registros de Internet han sido establecidos con la finalidad de hacer cumplir los objetivos de exclusividad, conservación, asignación de rutas e información. Este sistema consiste de Registros de Internet (IR) organizados jerárquicamente.  Los espacios de direcciones IPv4 son típicamente asignados a los usuarios finales por los ISPs o los NIRs.

Cuando el espacio libre de LACNIC alcance el equivalente a un /10 (aproximadamente   4.2   millones   de   direcciones), las   políticas relacionadas con el agotamiento entran en funcionamiento. Estas son las etapas cuando se alcance este límite:

- Período soft-landing
- Recursos para nuevos entrantes
- Agotamiento final

El protocolo IPv4 cuenta de 4 fase fundamentales para su finalización a continuación presentare el número de fase con su respectiva explicación:

**Fase 0**

Se inicia cuando entra en vigencia la fase de agotamiento hasta llegar al espacio equivalente al último.

1.	Las solicitudes son tratadas en el orden de llegada mediante un sistema de tickets. Solo el NIR de México (NIC.MX), como el de Brasil (NIC.br), administran sus tickets de forma independiente de LACNIC.
2.	Cualquier solicitud que este incompleta requerirá de información adicional de parte del que lo solicita, pasando al final de la de tickets y siendo respondida una vez que haya enviado toda la información requerida.
3.	Se evalúa las solicitudes tomando en cuenta el manual específicamente en el capitulo 2, otorgadas en base a la necesidad justificada.
4.	Si las solicitudes son iguales o mayores a un 15% son evaluadas tanto con los NIRs y LACNIC.
5.	Si son iguales /16 las solicitudes son evaluadas por dos hostmaster dentro de una misma entidad.
6.	Una vez que se aprueba la solicitud se procede a asignar la dirección, las cuáles son asignadas por un hostmaster de la propia entidad.

**Fase 1**

1.	Comenzará cuando se alcance un equivalente al último bloque /9, incluidos los dos reservados para la terminación gradual de IPv4 y para nuevos entrantes.
2.	Se efectúan los pasos 1 y 2 de la fase 0.
3.	Cumplido todos los requisitos, un hostmaster carga los datos de la solicitud en un formulario web con la siguiente información:
•	Número de Ticket
•	Fecha y hora UTC de ingreso de la solicitud.
•	Fecha y hora UTC de aprobación de la solicitud.
•	Organización y ownerID
•	Bloque pre - aprobado 
4.	La información se envía a un sistema de pre - aprobación el cual ordena de las más antigua a la mas nueva, claro esta tomando en cuenta la fecha cuando se creó el ticket. Se trabaja con la asignación de pre - aprobaciones.
5.	Si se tratase de una solicitud adicional se le asigna el siguiente día hábil de cuando fue hecha el pre – aprobación.
6.	Para la evaluación se repite los pasos 3,4 y 5 de la fase 0.

**Fase 2**

1.	Inicia cuando se alcance el último bloque /10. En esta fase se activa el punto 11.2 del manual de políticas, donde se reservará un bloque de prefijo /11 para una terminación gradual.
2.	En esta etapa, sólo se podrán asignar bloques desde un prefijo /24 hasta un /22, pudiendo recibir un bloque adicional cada 6 meses. Esta mecánica se llevará de igual forma todos los días hasta que llegue el momento en que termine el /11 reservado para terminación gradual.
3.	El manejo de solicitudes se tratará igual que la Fase anterior, siguiendo los paso del 1 al 6.
4.	Como criterios de evaluación las solicitudes serán tratadas de acuerdo a lo estipulado en el capítulo 11.2 del manual de políticas y deberán cumplir los requisitos de solicitud inicial o adicional establecidos en el capítulo 2 del manual de políticas.
5.	Es importante destacar que a partir de este momento dejan de existir análisis conjuntos entre LACNIC y NIRs para solicitudes de IPv4 y tampoco se hacen solicitudes en conjunto entre hostmasters dentro de los NIRs o LACNIC.
6.	Las asignaciones serán realizadas directamente por el hostmaster al siguiente día hábil de ser realizada su pre - aprobación.

**Fase 3**

Inicia cuando se agote el bloque /11 de terminación gradual.  Esta reserva será el último espacio disponible de LACNIC, el cual está compuesto de una reserva de prefijo /11 junto con bloques IPv4 que fueron recuperados. De este espacio solo se podrán hacer asignaciones entre un /22 y un /24. Cada nuevo miembro podrá recibir solamente una asignación inicial de este espacio.

El manejo de solicitudes se tratará igual que la Fase 0, siguiendo los paso del 1 al 2.

Como criterios de evaluación las solicitudes serán tratadas de acuerdo a lo estipulado en el capítulo 11.1 del manual de políticas y deberán cumplir los requisitos de solicitud inicial establecidos en el capítulo 2 del manual de políticas. En esta fase es importante aclarar que sólo se tomarán en cuenta las solicitudes iniciales.  Las asignaciones serán realizadas directamente por el hostmaster de cada entidad.

Soluciones paliativas:

- 1992 – La IETF crea el grupo ROAD (ROuting and ADdressing).

- CIDR (RFC 4632)

- Fin del uso de clases = bloques de tamaño apropiado.
- Dirección de red = prefijo/longitud.
- Agregación de rutas = reduce el tamaño de la tabla de rutas.
- DHCP
- Distribución de direcciones dinámicas.
- NAT + RFC 1918
- Permite conectar toda una red de computadoras usando una 
sola dirección válida en Internet, pero con algunas restricciones.

### **2.2	Direccionamiento IPv6**

La principal característica y mayor justificación para el desarrollo del protocolo IPv6 es el aumento del espacio de direccionamiento. Por este motivo es importante conocer las diferencias entre las direcciones IPv4 e IPv6, saber reconocer la sintaxis de las direcciones IPv6 y conocer los tipos de direcciones IPv6 que existen y sus principales características.

IPv6 tiene un espacio de direccionamiento de 128 bits, lo que permite obtener 340.282.366.920.938.463.463.374.607.431.768.211.456 direcciones (2128). Este valor representa aproximadamente 7,9x1028 de direcciones más que IPv4, y más de 5,6x1028 de direcciones por cada ser humano en la Tierra si consideramos una población estimada en 6 mil millones de habitantes.

La representación de las direcciones IPv6 divide la dirección en ocho grupos de 16 bits, separados mediante “:”, escritos con dígitos hexadecimales.

2001:0DB8:AD1F:25E2: CADE: CAFE: F0CA:84C1

En la representación de una dirección IPv6 está permitido:
- Utilizar caracteres en mayúscula o minúscula;
- Omitir los ceros a la izquierda; y
- Representar los ceros continuos mediante “::”.

**Ejemplo:**

2001:0DB8:0000:0000:130F: 0000:0000:140B

2001:db8:0:0:130f:140b

Formato no válido: 2001:db8::130f::140b (genera ambigüedad)

**Representación de los prefijos**

Como CIDR (IPv4)

“dirección-IPv6/tamaño del prefijo”

**Ejemplo:**

Prefijo 2001:db8:3003:2::/64

Prefijo global 2001:db8::/32

ID de la subred 3003:2

**URL**

http://[2001:12ff:0:4::22]/index.html

http://[2001:12ff:0:4::22]:8080

### **2.3	Formato de las direcciones IPv6**

El tamaño y el formato de la dirección IPv6 amplían la capacidad del espacio para direcciones.

El tamaño de las direcciones de IPv6 es de 128 bits. La representación preferente de direcciones de IPv6 es x:x:x:x:x:x:x:x, donde cada x es el valor hexadecimal de las 8 partes de 16 bits de la dirección. Las direcciones IPv6 abarcan desde 0000:0000:0000:0000:0000:0000:0000:0000 a ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff.

Además de en este formato preferente, las direcciones IPv6 pueden especificarse en otros dos formatos abreviados: 

**Omitir ceros iniciales.**

Especifique las direcciones IPv6 omitiendo los ceros iniciales. Por ejemplo, la dirección IPv6 1050:0000:0000:0000:0005:0600:300c:326b puede escribirse como 1050:0:0:0:5:600:300c:326b.

**Dos signos de dos puntos.**

Especifique las direcciones IPv6 con dos signos de dos puntos (::) en lugar de una serie de ceros. Por ejemplo, la dirección IPv6 ff06:0:0:0:0:0:0:c3 puede escribirse como ff06::c3. Los dos signos de dos puntos sólo pueden utilizarse una vez en una dirección IP.

Un formato alternativo para las direcciones IPv6 combina la notación de dos puntos y un punto, de forma que la dirección IPv4 puede incrustarse en la dirección IPv6. Se especifican valores hexadecimales para los 96 bits de más a la izquierda, y valores decimales para los 32 bits de más a la derecha que indican la dirección IPv4 incrustada. Este formato garantiza la compatibilidad entre los nodos IPv6 y los nodos IPv4 cuando se está trabajando en un entorno de red mixto.

La dirección IPv6 correlacionada con IPv4 utiliza este formato alternativo. Este tipo de dirección se utiliza para representar los nodos IPv4 como direcciones IPv6. Permite que las aplicaciones de IPv6 se comuniquen directamente con las aplicaciones de IPv4. Por ejemplo, 0:0:0:0:0:ffff:192.1.56.10 y ::ffff:192.1.56.10/96 (formato abreviado).

Todos estos formatos son formatos de dirección IPv6 válidos. Puede especificar estos formatos de dirección IPv6 en System i Navigator, excepto la dirección IPv6 correlacionada con IPv4.

### **2.4	Prefijos de subred**

**Notación de los prefijos**

- Esta notación está descrita en la RFC 4291 "IP Version 6 Addressing Architecture".

- Un prefijo es un conjunto de bits (en la zona de mayor peso) en una dirección IPv6, que se utiliza para identificar subredes o el tipo de dirección.

- El nombre exacto que reciben estos bits es “prefijo de enrutado global”.

- La notación de prefijo es muy similar a la forma en que se escriben las direcciones IPv4 en notación CIDR (Classless Interdomain Routing), indicando detrás de la dirección IP el número de bits que determinan el ID de la red (192.168.0.10/24 equivale a una máscara 255.255.255.0):

- En IPv6 tenemos:

        Dirección IPv6 / Longitud del prefijo

- El campo “Longitud del prefijo” especifica cuantos bits de la parte izquierda de la dirección forman el prefijo.

- Gracias al prefijo, los routers saben cómo dirigir los paquetes que les llegan hacia su destino correcto en una subred determinada.

- Un ejemplo, en la siguiente dirección IPv6, puesto que cada carácter hexadecimal consta de 4 bits, el prefijo es la parte marcada en azul (10 caracteres hexadecimales):

        2E78:DA53:1200::/40

- La notación abreviada (sustitución de ceros con un doble “:”) se puede aplicar también a la representación del prefijo, siguiendo las reglas ya explicadas.

**Prefijos de enrutado global**

- En este enlace se puede ver cómo organiza la IANA los prefijos reservados y las direcciones especiales (direcciones de enlace local, multicast...).

- Vamos a comentar algunos de estos prefijos:

    - 0000::/8 → Las direcciones que empiezan con 8 ceros están reservadas para la IETF.

    - 2000::/3 → Direcciones Unicast Globales. Estas serán todas aquellas direcciones cuyos 3 primeros dígitos binarios (los de mayor peso) sean 001.

    - Estas son las direcciones Unicast que gestiona la IANA. A efectos prácticos serían como las direcciones públicas que venimos usando con IPv4.

    - FC00::/7 → Dirección Unicast Local Única (ULA = Unique Local Unicast Address). Son direcciones cuyos 7 bits de mayor peso son 1111 110.

    - FE80::/10 → Dirección Unicast de Enlace Local. Aquellas cuyos primeros 10 bits son 1111 1110 10.

    - FF00::/8 →Direcciones Multicast. Aquellas cuyos 8 primeros bits son 1.

- En cuanto a las direcciones Anycast, se toman del rango de direcciones Unicast, por lo tanto, no es posible saber si una dirección es Anycast tan solo con mirar su prefijo.

### **2.5	Clasificación de direcciones IPv6**

En IPv6 se han definido tres tipos de direcciones:
- Unicast → Identificación Individual
- Anycast → Identificación Selectiva
- Multicast → Identificación en Grupo
- No existen más las direcciones Broadcast.

**Unicast:** Este tipo de dirección identifica una única interfaz, de modo que un paquete enviado a una dirección unicast se entrega a una única interfaz.

**Anycast:** Identifica un conjunto de interfaces. Un paquete enviado a una dirección anycast se entrega a la interfaz perteneciente a este conjunto más próxima al origen (de acuerdo con la distancia medida por los protocolos de encaminamiento). Las direcciones anycast se utilizan en comunicaciones de "uno" a "uno-de-muchos".

**Multicast:** También identifica un conjunto de interfaces, pero un paquete enviado a una dirección multicast se entrega a todas las interfaces asociadas a esa dirección. Las direcciones multicast se utilizan en comunicaciones de "uno" a "muchos".

### **2.6	Reglas de escritura**

Los ceros iniciales en un grupo también se pueden omitir. Por ejemplo, el grupo 0074 de la dirección ejemplo sería igual a 74, el grupo 000F se representará como F, y el grupo 0000 sería igual a 0. De manera que la dirección anterior puede expresarse en forma abreviada como: 

- FDEC :BA98:0074:3210:000F:0000:0000:FFFF
- FDEC:BA98:74:3210:F:0:0:FFFF

Uno o varios grupos nulos consecutivos pueden comprimirse como "::". Este método de abreviatura sólo puede utilizarse una vez en una dirección. Si la dirección tiene más de una serie de grupos nulos consecutivos la compresión sólo se permite en uno de ellos, por tanto, una forma más abreviada aún de expresar la dirección anterior que tiene ceros consecutivos sería:

- FDEC : BA98:74:3210:F: :  FFFF

**La dirección IPv6** 

- FDEC :0:74:3210:F : 0 : 0 :FFFF Podría abreviarse como FDEC : : 74 :3210:F: 0 : 0 : FFFF 

**O bien como:**
- FDEC:0: 74:3210:F::FFFF

Pero la dirección FDEC: :74:3210:F : : FFFF no es válida porque no queda claro cuántos grupos nulos representa cada uno de los “::”. 

La dirección IPv6 de loopback 0:0:0:0:0:0:0:1, y la dirección IPv6 indefinida 0:0:0:0:0:0:0:0 se reducen a ::1 y ::, respectivamente.

Utilizando una notación mixta formada por una parte de dirección IPv6 (6 grupos hexadecimales de 16 bits separados por dos puntos) y otra de IPv4 (4 decimales de 8 bits separados por puntos) Durante la transición de Internet de IPv4 a IPv6 será típico operar en entornos de doble direccionamiento (IPv4 e IPv6). Por este motivo se ha introducido esta notación mixta para expresar direcciones IPv6 a partir de direcciones IPv4 representando los últimos 32 bits de la dirección IPv6 en el formato decimal con puntos usado en IPv4. 

Por ejemplo, si la dirección decimal IPv4 es 135.75.43.52 (en hexadecimal, 0x874B2B34), puede ser convertida a la dirección IPv6 0000:0000:0000:0000:0000:FFFF:874B:2B34 ó ::FFFF:874B:2B34. 

Entonces, se puede usar la notación mixta, en cuyo caso la dirección debería ser :: FFFF:135.75.43.52. 

Direcciones IPv6 en URLs: Cuando se quiere escribir una dirección IPv6 en una URL, la dirección debe ir entre corchetes (por ejemplo, http:// [2001:720::212: 6BFF:FE11:1111]: 80/index.html) ya que los dos puntos se utilizan para indicar opcionalmente el número de puerto.

### **2.7	Direcciones especiales**

Versión 6 ha sido un poco compleja estructura de dirección IP que en IPv4. IPv6 ha reservado algunas direcciones y dirección notaciones de propósitos especiales. Consulte la tabla que aparece a continuación:

![2](/Dispositivos_de_Transmisión/2.png) 

Como se muestra en la tabla, la dirección 0:0:0:0:0:0:0:0/128 no especifica nada y se dice que es indeterminado. Después simplificar, todos los 0s son compactados a ::/128.

En IPv4, la dirección 0.0.0.0 con máscara 0.0.0.0 representa la ruta por defecto. El mismo concepto se aplica también a IPv6, la dirección 0:0:0:0:0:0:0:0 máscara con todos los 0s representa la ruta por defecto. IPv6 Después de aplicar regla, esta dirección se comprime a ::/0.

Las direcciones de loopback en IPv4 son representados por 127.0.0.1 a 127.255.255.255. Pero en el IPv6, sólo 0:0:0:0:0:0:0:1/128 representa la dirección de bucle. Una vez dirección de retorno de bucle, que se puede representar como ::1/128.

**Reservados Dirección de multidifusión para los protocolos de enrutamiento**

![3](/Dispositivos_de_Transmisión/3.png) 

El cuadro anterior muestra la reserva las direcciones de multidifusión de protocolo de enrutamiento interior.

Las direcciones están reservadas por el mismo reglamento de IPv4.

**Reservados Dirección de multidifusión para los Routers/Nodo**

![4](/Dispositivos_de_Transmisión/4.png) 

Estas direcciones a los routers y hosts para hablar con los routers disponibles y de los hosts en un segmento sin ser configurado con una dirección Ipv6. Los hosts utilizan EUI-64 base configuración automática para configurar automáticamente una dirección IPv6 y, a continuación, hablar a los hosts/routers del segmento por medio de estas direcciones.

## **3. Conclusiones**

Gracias a la existencia de estas políticas se prevé una mejor administración de recursos para un agotamiento gradual de IPv4, así como también el permitir acceso a nuevos actores que quieran iniciar sus actividades de Internet en un futuro. Como consecuencia de este agotamiento habrá un Mercado de direcciones IP, lo que significa la compra de IPs y cada vez va a resultar más costoso tener IPv4

Desplegar el protocolo IPv6 adquiere hoy más que nunca un sentido de urgencia, volviéndose inevitable e inaplazable si los proveedores de conectividad desean satisfacer la demanda de sus clientes y de nuevos usuarios. A pesar de que el 67% de las entidades miembros de LACNIC y los Registros Nacionales NIC.br y NIC.MX. ya cuentan con direcciones IPv6 asignadas es preocupante ver que hay muchos operadores y empresas que todavía no han dado los pasos necesarios para afrontar debidamente esta circunstancia. 

Internet crece a pasos agigantados y cada vez surgen más oportunidades de negocios.  Se estima que en nuestra región habrá decenas de millones de nuevos usuarios de Internet en el próximo año.  Para poder satisfacer la demanda de los siguientes años, es indispensable la implementación de IPv6 en todas las redes de acceso y en los servicios de contenidos de nuestra región.

## **4. Bibliografía**

Castillo, Y. (2014). Agotamiendo IPv4 en la región latinoamericana. Prisma Tecnológico, 5(1), 26-28.

Formatos de dirección de IPv6. (2021, 8 marzo). © Copyright IBM Corp. 1998, 2010. https://www.ibm.com/docs/es/i/7.1?topic=concepts-ipv6-address-formats

Gumuzio, I. (2009, 20 octubre). 2.2.1. Los prefijos - IPv6. sites google. https://sites.google.com/site/tknikaipv6/2-direccionamiento/2-2-direccionamiento/2-2-1-prefijos-de-enrutamiento-global

Nureña, G., Enriquez, A. (2014). Diseño Lógico de la Migración de IPV4 a IPV6 de la Red de Datos de la Universidad Nacional de Trujillo [Tesis, Universidad Nacional de Trujillo]. http://dspace.unitru.edu.pe/handle/UNITRU/11301

Patiño Sánchez, J. R. (2017). Análisis del direccionamiento IPv6 y estudio de los Protocolos de Enrutamiento orientados a IPv6. Maskana, 7(Supl.), 221–226. Recuperado a partir de https://publicaciones.ucuenca.edu.ec/ojs/index.php/maskana/article/view/1095

dos Santos, R. R., Moreiras, A. M., Reis, E. A., & da Rocha, A. S. (2010). Curso IPv6 básico. Recuperado a partir de http://ipv6. br/media/arquivo/ipv6/file/26/Apostila_Teorica_es. pdf.
