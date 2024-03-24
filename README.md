# Introducción a Phyton y MicroPython

# Problema a resolver

# Proceso de Construcción fisica
Para la construccion de un radar mediante LEGO inspirado en los radares 360 típicos de la aviación o de submarinos , se empleo un diseño que combine la facilidad de las piezas de LEGO con el funcionamiento de servomotores y un sensor ultrasónico. En primer lugar, se diseño  una base utilizando piezas que garanticen estabilidad en el sistema operativo, esta base esta especialmente diseñada para sostener el brick de LEGO de forma segura y estable. Esta base es esencial para asegurar que el radar pueda operar sin riesgo de caídas o desequilibrios durante su funcionamiento.

Una vez completada la base, se procede a montar una plataforma giratoria sobre ella mediante un motor adecuado. Este motor se adapto de manera que  permite el  movimiento giratoria de la plataforma en un rango completo de 360 grados. Esta capacidad de giro es esencial para que el radar pueda explorar todo su entorno y detectar cualquier objeto que se encuentre en su alcance.

Luego, se integra el sensor ultrasónico en la parte superior de la estructura, asegurando su posición para maximizar su capacidad de detección. Es importante que el sensor ultrasónico tenga una vista libre y sin obstrucciones estructurales  para garantizar mediciones precisas y fiables. Por lo tanto, se asegura de que no haya obstáculos que puedan bloquear su campo de visión, permitiéndole detectar objetos en todas las direcciones sin interferencias.

Por otro lado, se resolvió un problema en el diseño ya que los cables de conexión para el servomotor, sensor y para que se conectara a la computadora tuvieron que ser acomodados con base a que se pudiera lograr el movimiento adecuado sin tener alguna interferencia hacia el motor o alguna desconexión en el proceso para que todo pudiera funcionar de manera correcta 

Una vez que se han ensamblado todas las partes, el radar de LEGO está listo para su uso. Al activarlo, el motor comienza a girar la plataforma, mientras que el sensor ultrasónico escanea continuamente el entorno en busca de objetos. Cualquier objeto detectado se registra y se imprime en en base al código establecido al brick. Este método de construcción ofrece una experiencia de construcción creativa hacia la ingeniería y funcionalidad, demostrando el potencial de las piezas de LEGO para la creación de dispositivos prácticos e innovadores.

# Metodologia

Para el funcionamiento del codigo del radar nos encontramos con el gran reto de ser los primeros en desarrollar un codigo de radar con el brick de lego en micropython. Ya que al investigar por recursos para una guia u orientacion, estos no existian. Gracias a eso, nos dimos a la tarea de poder desarrollar un mapa en Python, para ello utilizamos el Software Visual Studio, donde instalariamos el add-on de Lego EV3 MicroPython, donde este softtware nos ayudara a conectar con el brick de Lego, pero para programar en Python es necesario flashear una tarjeta SD con el software de LEGO EV3 Classroom App v. 1.5.3. para ingresarla en el brick y este este configurado y adaptado para poder ser usado en Visual Studio. Posterior a ello empezamos creamos diversos proyectos nuevos con la finalidad de probar los codigos creados. Es importante mencionar que la estructura del radar tiene que ya estar hecho o diseñada, ya que al momento de probar el funcionamiento del codigo es menester observar que se ejecute de manera correcta. 
Al momento de crear un mapa nos encontramos con muchos problemas con el sistema operativo ya que todo el programa se configuro en Visual Studio Code for Windows por lo que no se contaban con muchas librerias a comparación de la version de Linux donde se puede usar la funcion 'plt' y otras librerias que nos ayudarian a formar un grafico de pastel y eso ayudaria mucho al crear un mapa de 360°. Entonces necesitabamos crear un mapa sin ninguna de estas funciones o librerias por lo que se me ocurrio la idea de generar un mapa de texto, entonces la unica forma de crear un mapa sin librerias externas fue hacer un mapa de texto por lo que creamos una matriz de -50 a 51 para que tuviera un rango amplio al imprimir los objetos, con ello logramos imprimir el mapa de texto que es en forma rectangular, en medio un emoji de robot para identificar que esta en el centro y en las coordenadas (0,0) con ello podemos interpretar el mapa y en donde estan los objetos muestreados, para el sonar lo que hicimos fue configurarlo junto con el servomotor ya que estos se movian y capturaban cada 10° por lo que hace un muesteo total 36 veces en lapso de 8-10 segundos. El diseño de la estructura fue a creatividad nuestra tomando cuenta el peso de las 2 estructuras construidas, la primera estructura es la base que sostiene el servomotor y hace funcion de que este servomotor quede inmovil y su movimiento y vibración no afenten la estabilidad y que en el momento que empiece a balancearse la segunda estructura con los giros, esta no se caiga. Para la segunda estructura Se hizó una base que se acoplara al servomotor y de igual manera esta no quede endeble ni se balancee tanto al momento de tener su movimiento. Se destaca el uso de creatividad y aprendizajes en clase ya que sin estas características este proyecto no se hubiera logrado.


# Funcionamiento del Codigo Radar

CODIGO FINAL FINAL VERSION ULTIMATE LEON & FORNE'S CODE

### Se usaron todas las librerias para asegurar que no hubiera ningun tipo error.

#!/usr/bin/env pybricks-micropython

from pybricks.hubs import EV3Brick
from pybricks.media.ev3dev import SoundFile, ImageFile

import math

### Asignamos un puerto para el Servomotor y el Sensor ultrasonico

#Configuración del motor y el sensor

motor = Motor(Port.B)

ultrasonic_sensor = UltrasonicSensor(Port.S2)

### Congiguramos el sonar y servomotor para que se muestre cada 10°, la velocidad de servo y la distancia que capta el sonar 

#Función para escanear el entorno

def scan_environment():
    def scan_environment():

    return obstacles

### Creacion del mapa donde establecemos su tamaño, la posición del robot en el mapa y los obstaculos muestreados.

def generate_obstacle_map(obstacles, robot_position):

    for y in range(50, -51, -1):
      def generate_obstacle_map(obstacles, robot_position):
       
        print(row)

### Imprimimos el mapa en la terminal
Comment
 
Leave a comment
 

#Escanear el entorno y generar el mapa de obstáculos

robot_position = (0, 0)  # Posición inicial del robot (suposición)

Muestra del funcionamiento del Radar:

https://youtube.com/shorts/lXxNpzi4Lq8

# Conclusiones



