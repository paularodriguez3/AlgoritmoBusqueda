# TRABAJO ALGORITMO DE BÚSQUEDA 

 ### **Contenido del repositorio:** 
- **run.py:** Contiene el programa principal que realiza búsquedas en diferentes estrategias.
- **search.py:** Contiene la implementación de clases y funciones relacionadas con la búsqueda, incluyendo el problema de búsqueda y los algoritmos de búsqueda.
- **utils.py:** Contiene funciones y utilidades auxiliares utilizadas en el programa.

### **Algoritmos de búsqueda implementados:**
- **breadth_first_graph_search:** Búsqueda en amplitud.
- **depth_first_graph_search:** Búsqueda en profundidad.
- **branch_and_bound_graph_search:** Búsqueda en ramificación y acotación.
- **branch_and_bound_subestimated_graph_search:** Búsqueda en ramificación y acotación subestimada.

### **Problemas de ejemplo:**
El programa incluye ejemplos de problemas de búsqueda en el archivo *run.py*. Estos ejemplos están definidos en la variable *ab* y se refieren a un problema en el que se busca una ruta en un mapa de Rumanía (representado en un grafo dentro del archivo *search.py*), desde un punto de inicio hasta un punto de destino.

## **Método BRANCH AND BOUND (Algoritmo de búsqueda en ramificación y acotación) añadido:**

- **Inicialización:** Se comienza con un conjunto de nodos inicial que se representan mediante una cola de prioridad *A*. Cada nodo en esta cola tiene asociado un costo de ruta para llegar a ese nodo desde el nodo inicial. Los nodos se insertan en la cola utilizando el método *append* o *extend*.

- **Expansión de nodos (Ramificación):** El algoritmo expande el nodo en la parte delantera de la cola. La expansión implica generar los hijos de ese nodo, que representan posibles estados siguientes en el espacio de búsqueda.

- **Criterio de acotación (Bounding):** Antes de agregar los nodos hijos a la cola de prioridad, se realiza una comprobación para determinar si alguno de ellos puede ser descartado sin necesidad de explorarlo completamente. Esto se basa en comparar el costo de ruta del nodo hijo con un límite superior conocido hasta ese momento. Si el costo del nodo hijo supera el límite superior, se descarta.

- **Ordenamiento por costo de ruta:** Después de la expansión, los nodos resultantes se agregan a la cola de prioridad. Para garantizar que los nodos con menores costos de ruta se exploren primero, la cola se ordena en función de estos costos utilizando el método *extend*, garantizando que el nodo con menor costo de ruta esté en la parte delantera de la cola.

- **Extracción de nodos:** El método *pop* se utiliza para extraer el nodo con el menor costo de ruta de la parte delantera de la cola. Esto se hace ajustando el índice de inicio y actualizando la cola.

## **Método BRANCH AND BOUND SUBESTIMATED (Algoritmo de búsqueda en ramificación y acotación con subestimación) añadido:**

- **Inicialización:** Similar al método anterior, se inicia con un conjunto de nodos representado por la cola de prioridad *A*. Cada nodo tiene un costo de ruta asociado, pero en este caso, se utiliza una heurística subestimada para estimar el costo adicional desde ese nodo hasta la meta. El problema de búsqueda asociado se guarda en *self.problem*.

- **Expansión de nodos (Ramificación):** Al igual que en el algoritmo estándar, se expande el nodo en la parte delantera de la cola generando sus nodos hijos.

- **Criterio de acotación (Bounding) con heurística subestimada:** Antes de agregar nodos hijos a la cola de prioridad, se realiza una comprobación basada en la heurística subestimada. Se compara el costo de ruta acumulado más la estimación heurística del nodo actual con el costo de ruta acumulado más la estimación heurística de los nodos hijos. Si el costo estimado del nodo hijo supera el costo estimado del nodo actual, el nodo hijo se descarta sin explorarlo completamente.

- **Ordenamiento por costo de ruta con heurística subestimada:** Después de la expansión, los nodos resultantes se agregan a la cola de prioridad. Para garantizar que los nodos con menores costos de ruta estimados se exploren primero, la cola se ordena en función de la suma del costo de ruta acumulado y la heurística subestimada. El método *extend* garantiza que los nodos con la estimación más baja (costo acumulado más heurística) estén al principio de la cola.

- **Extracción de nodos:** El método *pop* se utiliza para extraer el nodo de mayor prioridad de la parte delantera de la cola. Se actualiza el índice de inicio y se ajusta la cola según sea necesario.


## **Autores:** ✒️
- Mauro Gómez Guillén
- Paula Rosa Rodríguez Morales

