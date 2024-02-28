# The L programming language

#### Una extensión del proyecto [Flex-Bison-Compiler](https://github.com/agustin-golmar/Flex-Bison-Compiler) 

## Compilación
Para construir el compilador, ejecutar en la raíz del proyecto los siguientes comandos

```bash
chmod u+x --recursive script
script/build.sh
```

## Testing
Para correr los programas de testeo (que se pueden encontar en `test/`), ejecutar el siguiente comando
```bash
script/test.sh
```

## Ejecución 
Si se desea correr al compilador con un programa (como `test/accept/01-simplecircuit`), ejecutar el siguiente comando
```bash
script/start.sh test/accept/01-SimpleCircuit
```
### Archivo de salida
Es posible indicar el nombre del archivo donde se desea guardar la compilación.
Para ello, se debe agregar un segundo parámetro al comando anterior, indicando el nombre del archivo de salida.
```bash
script/start.sh test/accept/01-SimpleCircuit out.py
```
En este caso, la compilación se guardará en el archivo `out.py`.
<br>
<br>
Si no se indica el nombre del archivo de salida, se guardará en `salida.py` por defecto.

### Utilizacion del codigo compilado
Para la utilizacion del codigo compilado resulta necesario ingresar por entrada estandart texto en formato csv con una entrada por fila.
La salida del progrma se realizará por la salida estandart.
En ambos casos se podrá y se recomienda la utilizacion de archivos .csv y la utilizacion de utilidades de consola para la redireccion de las entradas y salidas del programa.
<br>
<br>
Ingresando un archivo como entrada al programa 
```bash
python3 salida.py < input.csv
```
Ingresando de forma manual una entrada al programa
```bash
printf "10101\n11111" | python3 salida.py
```
Obteniendo la salida por la terminal del usuario
```bash
python3 salida.py < input.csv
```
Obteniendo la salida en un documento .csv
```bash
python3 salida.py < input.csv > output.csv
```
### Conexion de diferentes programas
Una utilidad que le da mucha potencia al lenguaje es la posibilidad de interconetar script previamente compilados mediante el uso de la terminal.
```bash
python3 proc1.py < input.csv | python3 proc2.py > output.csv
```
Si se quiere activar los logs, se debe descomentar la siguiente línea en `src/backend/support/logger.h`
```c
#define DEBUG true
```

## Soporte

* Axel Facundo Preiti Tasat: https://github.com/AxelPreitiT
* Gastón Ariel Francois: https://github.com/francoisgaston
* José Rodolfo Mentasti: https://github.com/JoseMenta
