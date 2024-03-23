# Introducción a Phyton y MicroPython

# Problema a resolver

# Proceso de Construcción fisica

# Funcionamiento del Codigo Radar

Para el funcionamiento del codigo del radar nos encontramos con el gran reto de ser los primeros en desarrollar un codigo de radar con el brick de lego en micropython 



CODIGO FINAL FINAL VERSION ULTIMATE LEON & FORNE'S CODE

#!/usr/bin/env pybricks-micropython

from pybricks.hubs import EV3Brick

from pybricks.ev3devices import (Motor, TouchSensor, ColorSensor,

                                 InfraredSensor, UltrasonicSensor, GyroSensor)

from pybricks.parameters import Port, Stop, Direction, Button, Color

from pybricks.tools import wait, StopWatch, DataLog

from pybricks.robotics import DriveBase

from pybricks.media.ev3dev import SoundFile, ImageFile

import math

#Configuración del motor y el sensor

motor = Motor(Port.B)

ultrasonic_sensor = UltrasonicSensor(Port.S2)

#Función para escanear el entorno

def scan_environment():

    angles = range(0, 360, 10)
    
    obstacles = []
    
    for angle in angles:
    
        motor.run_target(500, angle)
        
        distance = ultrasonic_sensor.distance()
        
        if distance < 255:
        
            x = distance * math.cos(math.radians(angle))
            
            y = distance * math.sin(math.radians(angle))
            
            obstacles.append((x, y))
        
        wait(100)  # Breve pausa para estabilidad
    
    return obstacles

def generate_obstacle_map(obstacles, robot_position):

    for y in range(50, -51, -1):
    
        row = ''
        
        for x in range(-50, 51):
        
            is_obstacle = False
            
            for obstacle_x, obstacle_y in obstacles:
            
                distance = math.sqrt((obstacle_x - x) ** 2 + (obstacle_y - y) ** 2)
                
                if distance < 5:  # Umbral de distancia #5 es lo recomendado
                
                    is_obstacle = True
                    
                    break
            
            if (x, y) == robot_position:
            
                row += '🤖'  # Representación gráfica de la posición del robot
            
            elif is_obstacle:
            
                row += 'X'
            
            else:
            
                row += ' '
       
        print(row)

#Escanear el entorno y generar el mapa de obstáculos

robot_position = (0, 0)  # Posición inicial del robot (suposición)

obstacles = scan_environment()

generate_obstacle_map(obstacles, robot_position)

# Conclusiones



