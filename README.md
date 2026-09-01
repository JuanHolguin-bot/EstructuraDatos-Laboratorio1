Laboratorio 1:  Optimización de Memoria para Matriz Masiva (100,000 x 100,000)

Estudiante: Juan Sebastián Holguín Suárez   

---
Descripción: 
Este repositorio resuelve el desafío de procesar, almacenar y verificar una matriz masiva de 100,000 × 100,000 elementos (10,000 millones de datos) evitando el colapso de la memoria RAM, escritura optimizada por bloques y lectura secuencial.

## Archivos del Repositorio
`matrix100k.py`: Script encargado de construir eficientemente las filas de la matriz y escribirlas de manera secuencial en un archivo de texto plano (`matriz_gigante.txt`) en el disco duro. 
  1. Composición Horizontal de las Filas
    Cada fila del archivo es una secuencia continua de texto horizontal compuesta exactamente por 100,000 elementos numéricos separados por comas (,). Se definen dos tipos de filas base:
      Fila de ceros (fila0): Una secuencia de 100,000 ceros consecutivos (0,0,0,...,0).
      Fila de unos (fila1): Una secuencia de 100,000 unos consecutivos (1,1,1,...,1).

  2. Separación Vertical por Saltos de Línea
    Para convertir estas cadenas horizontales en una matriz estructurada, se utiliza el carácter de salto de línea (\n) como delimitador. Cada 100,000 elementos, el sistema inserta un salto de línea, lo que permite apilar los registros verticalmente uno debajo del otro.

`Lector.py`: Script diseñado para leer el archivo gigante por bloques o líneas, permitiendo verificar que cada fila contenga exactamente los 100,000 registros esperados sin consumir memoria excesiva, es decir está diseñado para verificar que si hayan 100,000 registros en cada fila

¿Cómo verificar el contenido de la matriz?
Los métodos usados fueron. 
1. El archivo `Lector.py` para verificar cantidad de columnas.
2. Por consola usar comandos para contar la cantidad de separadores de filas y verificar que hayan 100,000 o 99,999 si no se tiene en cuenta el último.


Por fines de practicidad y en el contexto de Linux, en clase se usó como separador entre cada fila el carácter "|"; (0,0,...,0) | (1,1,...,1), se puede ver ilustrado en (Imagen 1), lo cual fue posible ver usando el comando `head -n 2 matriz_gigante.txt
`, que sirve para mostrar únicamente las dos primeras filas del archivo. 

Luego para verificar que si hayan 100,000 filas, se usó el comando `grep -o '|' matriz_gigante.txt | wc -l` para contar la cantidad de "|" que existían en el archivo, lo que es igual a la cantidad de filas. 
    - `grep -o '|' matriz_gigante.txt | wc -l`: Cuenta el número exacto de separadores (|) en todo el archivo; `grep -o` aísla cada coincidencia en una línea independiente y `wc -l` cuenta el total de líneas resultante, el resultado dio 100,000, lo que confirma que si hay 100,000 filas en la matriz (Imagen 2). 
  
