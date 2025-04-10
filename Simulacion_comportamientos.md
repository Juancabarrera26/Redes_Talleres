
Simulación 

Objetivos

Simular y analizar el comportamiento de distintos tipos de nodos en una red inalámbrica a través de un programa desarrollado en Python.

Objetivos Específicos:
Simular 5 nodos con comportamiento altruista.

Simular 5 nodos con comportamiento egoísta.

Simular 5 nodos con comportamiento cooperativo utilizando concurrencia (multitarea).

Mostrar estadísticas de comportamiento y rendimiento de cada nodo.

Analizar el impacto de cada comportamiento en la red simulada.

Desarrollo de la Simulación
La simulación consiste en crear 15 nodos en total:

Tipo de Nodo	Cantidad	Característica Principal
Altruista	5	Ayuda a retransmitir paquetes de otros nodos.
Egoísta	5	Solo se preocupa por enviar sus propios paquetes.
Cooperativo	5	Realiza tareas en paralelo o concurrentes.
El comportamiento de cada nodo fue implementado mediante una clase en Python llamada Nodo, con sus respectivos métodos para enviar paquetes o ejecutar tareas concurrentes.

Los nodos altruistas ayudan a otros nodos a enviar sus paquetes. Los nodos egoístas simplemente envían su propio paquete sin colaborar con los demás. Por último, los nodos cooperativos ejecutan varias tareas de forma paralela utilizando la librería threading de Python, lo cual simula un uso eficiente de recursos computacionales.

Explicación del Código
El programa está dividido en las siguientes partes:

Definición de la clase Nodo con atributos: id, tipo, paquetes_enviados y paquetes_ayudados.

Método enviar_paquete() que controla el comportamiento según el tipo de nodo.

Método ejecucion_concurrente() para los nodos cooperativos, donde se ejecutan 3 tareas simultáneas utilizando hilos.

Creación de los 15 nodos y ejecución de 3 rondas de simulación donde todos los nodos interactúan.

Mostrar al finalizar las estadísticas generales de la red.

El lenguaje utilizado es Python por su simplicidad y versatilidad, además de contar con soporte para programación concurrente.

Resultados Obtenidos
Al ejecutar el programa, se observaron los siguientes comportamientos:

Los nodos altruistas colaboraron significativamente con los demás, aumentando su contador de ayuda.

Los nodos egoístas realizaron un mínimo de interacción, limitándose a sus propios envíos.

Los nodos cooperativos demostraron un uso eficiente de tareas en paralelo, completando múltiples procesos en menor tiempo.

Se obtuvieron estadísticas finales donde se muestra la cantidad de paquetes enviados por cada nodo y la cantidad de ayudas realizadas.

Conclusiones
Los nodos altruistas son esenciales en una red colaborativa ya que mejoran la conectividad y eficiencia general.

Los nodos egoístas representan un desafío, ya que solo buscan su propio beneficio, lo que puede perjudicar el rendimiento global de la red.

Los nodos cooperativos, mediante el uso de concurrencia, logran una mejor distribución de las tareas y optimización de recursos computacionales.

La simulación desarrollada permitió entender de manera práctica cómo influyen estos comportamientos en una red inalámbrica.
