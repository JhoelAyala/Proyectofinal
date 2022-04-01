# **Encendido de un Foco a 120 V Automáticamente**  

## **1. Introducción**

El campo de la electrónica es muy interesante y bonita, gracias a ella se puede lograr de pequeñas a grandes cosas, como en el presente trabajo por medio de la electrónica vamos a automatizar un foco de 120 V con la ayuda de un sensor de movimiento, dicho proyecto lo vamos a alimentar con una fuente capacitiva la cual no es necesario contar con un trasformador, ya que son muy grandes y para el trabajo necesitamos que todo sea mas compacto.

## **2. Desarrollo** 

***Arduino 1***

![1](/Electrónica_II/1.png)

***Microcontrolador ATMEGA328P***

![2](/Electrónica_II/2.png)

- **Botón Reset:**
Pulsador de Reset el cual permite reiniciar el C.I ATMEGA328P.

- **Programación serial en circuitos:**
Permite programar el C.I ATMEGA328P, nos brinda la comunicación entre el software y hardware.

- **Pines con modulación por ancho de pulso (PWM):**
Los pines digitales 3,5,6,9,10,11 se establece el PWM como salidas de 8 bits, a través de la función analogWrite. En si es una técnica que permite modificar ciclos de señales periódicas, también se utiliza mucho para la transferencia de datos por medio de un canal de comunicación o sirve también para el control de energía enviada a una carga específica.

- **Pines de puerto serial:**
Usados para recibir datos de un extremo (RX) y enviar datos a otro extremo (TX), siendo 0 y 1 respectivamente, teniendo conexión directa con C.I ATMEGA328P.

- **Interrupciones externas:**
Ubicadas en los pines 2 y 3, usados para interrupciones mediante valores bajos, ya sea de extremo ascendente o descendente, o por variación de valores.

- **Bus de la interfaz periférica serial - SPI:**
Estos SPI (Serial Peripheral Interface) ubicados en los pines 10 (SS), 11 (MOSI), 12 (MISO), 13 (SCK). Es un protocolo en serie sincrónico de datos usado por microcontroladores para la comunicación con uno o varios dispositivos periféricos de la forma más rápida, pero en distancias pequeñas. Usado también para que se comuniquen dos microcontroladores.

- **Conexión a tierra (GND):**
Pines que deben ir conectados a tierra, para tener un valor 0V.

- **Pines de tensión de referencia (AREF):**
Encargado de generar tensión de referencia para las entradas análogas.

- **Conector USB:**
Brinda la transmisión de datos a computadoras, dicho estándar no requiere de controladores externos. Para Windows es necesario los archivos .inf

- **Conector de alimentación externa:**
Conector tipo hembra (2.1mm) permite alimentar de energía a la tarjeta Arduino.

- **Pines para alimentación regulada a 3.3 V**  
Fuente de voltaje a 3,3 V generada en el chip FTDI integrado en la placa, soportando 50mA como corriente máxima.

- **Alimentación DC**
El voltaje usado para alimentar el microcontrolador y otros componentes de la placa es 5V.

- **Alimentación DC de entrada (Vin)**
Se la puede alimentar de una fuente de voltaje externa aparte de la alimentación por USB.

- **Entrada analógica (Analog In)**
Dispone de 6 de pines de entrada analógicas, en cada uno de sus pines suministra 10 bits.

- **Oscilador de cristal** 
Es usado para la señal de reloj para el funcionamiento del micro ATMEGA328P.

***Sensor de Movimiento (HC-SR501)***

![3](/Electrónica_II/3.png) ![4](/Electrónica_II/4.png)

Todo emite cierta radiación de bajo nivel, y cuanto más caliente es algo, mayor radiación es emitida. La presencia de personas, animales u objetos desprenden calor, son la base de cualquier sistema de detección de intrusos.

Los sensores infrarrojos pasivos son ideales para proyectos de detección de dichos movimientos. El sensor HC-SR501, sólo funciona cuando alguien se mueve en la franja que puede barrer su detector. Puede detectar movimiento de 3 hasta 7 metros de distancia. Este sensor de movimiento PIR tiene 3 pines, VCC, OUTPUT y GND, 2 potenciómetros para ajustar la sensibilidad y la demora. El retardo se puede configurar entre 5 y 300 segundos mientras que el potenciómetro de sensibilidad ajusta el rango de detección de aproximadamente 3 metros a 7 metros.

***Fotorresistencia***

![5](/Electrónica_II/5.png)

Componente electrónico que cuenta con una resistencia eléctrica puede cambiar de tamaño al entrar en contacto distintas intensidades de luz. Consiste en una célula fotorreceptora y dos pastillas. Cuando ya no detecta cierto nivel de luz (es decir, cuando cae por debajo de los lúmenes mínimos predefinidos), entonces hace contacto y los leds se encienden.

***Relay*** 

![6](/Electrónica_II/6.png) ![7](/Electrónica_II/7.png)


Un relé es un interruptor accionado por un electroimán.

Un electroimán está formado por una barra de hierro dulce, llamada núcleo, rodeada por una bobina de hilo de cobre. Al pasar una corriente eléctrica por la bobina el núcleo de hierro se magnetiza por efecto del campo magnético producido por la bobina, convirtiéndose en un imán tanto más potente cuanto mayor sea la intensidad de la corriente y el número de vueltas de la bobina. Al abrir de nuevo el interruptor y dejar de pasar corriente por la bobina, desaparece el campo magnético y el núcleo deja de ser un imán.

***Fuente Capacitiva***

![8](/Electrónica_II/8.png)

Para la mayoría de las aplicaciones electrónica, las fuentes de alimentación requieren que el voltaje de la red se baje con el fin de obtener un valor más aproximado para los circuitos alimentados en corriente continua. Esto normalmente se hace a través de un transformador, que es un componente caro, pesado y ocupa mucho lugar. Lo que muchos lectores pueden no saber es que existen alternativas al uso del transformador.

Una de las ventajas de usar un circuito sin transformador se centra en que se reduce bastante el coste, tamaño y peso siendo también una solución muy efectiva para aplicaciones que requieren baja potencia para su funcionamiento, como por ejemplo aplicaciones que requieren corriente por debajo de 100 mA.

Una idea inicial consiste en un divisor resistivo, por lo que la tensión de alimentación se reduce y después de eso, puede ser rectificada y filtrada, como se muestra en la siguiente figura.

Las cuatro partes de que se compone generalmente una fuente de alimentación sin transformador son principalmente el condensador de entrada de alto voltaje, tipo poliéster o cerámico, el rectificador, ya sea en media u onda completa, el estabilizador de la tensión fija que necesita el circuito de carga y el filtrado.

![9](/Electrónica_II/9.png)

***El condensador***

![13](/Electrónica_II/13.png)

Las especificaciones de voltaje de este condensador se seleccionan de tal manera que su clasificación de voltaje pico RMS es mucho mayor que el pico de la tensión de red de CA con el fin de garantizar el funcionamiento seguro del condensador. Este condensador se aplica en serie con una de las entradas de red, preferiblemente la línea de fase de la CA.

Cuando la red de corriente alterna AC entra en el condensador, dependiendo del valor del condensador, la reactancia del condensador entra en acción y restringe la corriente alterna de la red de exceder el nivel dado, según lo especificado por el valor del condensador.

El alto voltaje debe ser estabilizado mediante un diodo Zener en la salida, la potencia del diodo Zener debe seleccionarse adecuadamente de acuerdo con el nivel de corriente permitido del condensador. La función del diodo Zener es mantener entre sus terminales, ánodo y cátodo, una tensión fija y estable a partir de un rango de tensión mayor de la tensión de Zener. La corriente circula de cátodo a ánodo, en contra de la flecha, y el voltaje tiene el valor más positivo en el cátodo. El diodo Zener tiene un valor de tensión especifico que es el que mantiene a partir de una tensión continua.

![10](/Electrónica_II/10.png)

***Desventajas de usar una fuente capacitiva***

En primer lugar, el circuito no puede producir salidas de alta corriente, pero eso no será un problema para la mayoría de las aplicaciones.
Otro inconveniente que ciertamente necesita cierta consideración es que el concepto no aísla el circuito de las potencialidades peligrosas de la red de CA. Este inconveniente puede tener graves impacto para los diseños que tienen salidas terminadas o partes metálicas de metal, pero no importará para las unidades que tienen todo cubierto en una carcasa no conductora o de plástico.

***Veamos  la forma más típica de hacer una fuente capacitiva:***

![11](/Electrónica_II/11.png)

***Circuito realizado en Proteus***

![12](/Electrónica_II/12.png)

***Código realizado en Arduino***

~~~
int pinF = 0;
int valorF = 0;
int valor = 0;
int senPIR = 13;
int foco = 2;

void setup()
{
  
  pinMode(senPIR, INPUT);
  pinMode(foco, OUTPUT);
  
  Serial.begin(9600);
}

void loop()
{
  digitalWrite(foco, LOW);
  
  valor=digitalRead(senPIR);
  valorF=analogRead(pinF);
  
  Serial.println(valorF);
  
  if (valorF<910 && valor == HIGH)   
   { 
    digitalWrite(foco, HIGH);  

    delay(60000);

   } 

   ~~~
