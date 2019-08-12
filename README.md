# Buscar-el-centro-
'''
Descripción: Este programa esta diseñado con el fin de 
calcular el centro de un mundo donde Reeborg puede 
desplazarse unicamente en un eje.
Autores: MICHAEL GARZÒN - WILLIAM GUTIERREZ
Fecha: 08/08/2019

Pre: Robot inicia en (1,1) mirando al este.
Pos: Reeborg coloca la estrella en la mitad del 
mundo y llega a casa en (1,1) mirando hacia el sur 
u oeste
'''

def Findmiddle():
# Si hay una pared en frente, Reeborg gira.
    if wall_in_front():
        turn_left()
        contador=1
# Este primer while tien como funcion contar hasta
# que Reeborg se encuentre frente a una pared.
        while front_is_clear():
            move()
            contador=contador+1
        repeat 2:
            turn_left() 
# Divide el contador en dos para saber la mitad de las posiciones.
        middle = int(contador/2)
# Se descuentan la mitad de las posiciones.        
        while middle>0:
            move()
            middle=middle-1
        put("star")
# Reeborg se mueve hasta que el contador se haga 1
        while front_is_clear():
            move()
# Esta condicion es para cuando el frente ya esta claro.
    else:
        contador=1
        while front_is_clear():
            move()
            contador=contador+1  
        repeat 2:
            turn_left()            
        middle = int(contador/2)
        while middle>0:
            move()
            middle=middle-1
        put("star")
        while front_is_clear():
            move()
Findmiddle()
################################################################
# WARNING: Do not change this comment.
# Library Code is below.
################################################################
