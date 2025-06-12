## Simulación de Comportamientos en Redes Inalámbricas

En esta simulación consiste en una simulación desarrollada en Python donde se modelan diferentes comportamientos de nodos dentro de un entorno de red inalámbrica.

Se implementan tres tipos de comportamientos de nodos:

Nodos altruistas → Comparten recursos sin restricciones.

Nodos egoístas → Usan sus recursos solo para sí mismos.

Nodos cooperativos → Comparten recursos solo de manera controlada cuando detectan que otro nodo tiene recursos bajos.

La finalidad de esta simulación es observar cómo estos comportamientos afectan a la gestión de recursos dentro de una red.

## Lenguaje de Programación Utilizado
Python 3.x

## Estructura de la Simulación
Se simulan 15 nodos distribuidos así:

Tipo de Nodo	Cantidad de Nodos
Altruista	5
Egoísta	5
Cooperativo	5
Cada nodo inicia con 100 recursos y en cada ronda ejecuta su comportamiento según su tipo.

La simulación se desarrolla en 5 rondas.

Instrucciones de Ejecución
Tener instalado Python 3.x

Ejecutar el siguiente comando:

'''
import random

class Nodo:
    def __init__(self, id, tipo):
        self.id = id
        self.tipo = tipo  # altruista, egoista, cooperativo
        self.recursos = 100

    def consumir_recursos(self):
        consumo = random.randint(5, 15)
        self.recursos -= consumo
        if self.recursos < 0:
            self.recursos = 0

    def compartir_recursos(self, red):
        for nodo in red:
            if nodo.id != self.id:
                nodo.recursos += 5
                self.recursos -= 5
                if self.recursos < 0:
                    self.recursos = 0

    def compartir_controlado(self, red):
        for nodo in red:
            if nodo.id != self.id and nodo.recursos < 50:
                nodo.recursos += 5
                self.recursos -= 5
                if self.recursos < 0:
                    self.recursos = 0

    def comportamiento(self, red):
        if self.tipo == "altruista":
            self.compartir_recursos(red)
        elif self.tipo == "egoista":
            self.consumir_recursos()
        elif self.tipo == "cooperativo":
            self.compartir_controlado(red)
'''

# Crear la red de nodos
red = []

# Crear nodos altruistas
for i in range(5):
    red.append(Nodo(i, "altruista"))

# Crear nodos egoistas
for i in range(5, 10):
    red.append(Nodo(i, "egoista"))

# Crear nodos cooperativos
for i in range(10, 15):
    red.append(Nodo(i, "cooperativo"))

# Simulación de 5 rondas
for ronda in range(1, 6):
    print(f"\n--- Ronda {ronda} ---")
    for nodo in red:
        nodo.comportamiento(red)
        print(f"Nodo {nodo.id} ({nodo.tipo}) - Recursos: {nodo.recursos}")

print("\n--- Simulación Finalizada ---")
print("\nEstado final de los nodos:")
for nodo in red:
    print(f"Nodo {nodo.id} ({nodo.tipo}) - Recursos: {nodo.recursos}")
## Resultado Final
Al finalizar la simulación se obtiene un estado de recursos diferente para cada nodo, dependiendo de su comportamiento.

Se puede observar que:

Los nodos altruistas suelen quedarse sin recursos más rápido por compartir constantemente.

Los nodos egoístas mantienen recursos, pero no ayudan a los demás.

Los nodos cooperativos logran un equilibrio mejor al compartir solo cuando es necesario.

# Resultados

![Captura de pantalla 2025-04-09 222304](https://github.com/user-attachments/assets/5fde8694-8ab4-48b5-b0bd-ea26f40422a1)
![Captura de pantalla 2025-04-09 222313](https://github.com/user-attachments/assets/547c6f10-0ee2-4c4e-a669-c134c3531035)
![Captura de pantalla 2025-04-09 222322](https://github.com/user-attachments/assets/8ea5a989-6b49-4962-b30d-bdf84681ec97)
![Captura de pantalla 2025-04-09 222331](https://github.com/user-attachments/assets/fc930cbd-74fb-4c31-9302-8b315c571bcd)
![Captura de pantalla 2025-04-09 222342](https://github.com/user-attachments/assets/5df2788a-1b8f-4a70-9560-a80c53ff98d5)
![Captura de pantalla 2025-04-09 222351](https://github.com/user-attachments/assets/16136a54-5153-43a0-b339-4aaf6aa31330)
![Captura de pantalla 2025-04-09 222358](https://github.com/user-attachments/assets/79728496-42f0-4c14-9a3c-a4074a826b10)





