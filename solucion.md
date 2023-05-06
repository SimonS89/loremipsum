# Solución al ejercicio

* Creo repositorio en github
* Lo clono pegando la clave SSH
* Me voy a la carpeta loremipsum y creo una nueva rama con **git branch generarlipsum**
* Me paso a la rama nueva con **git checkout generarlipsum**
* Agregar el archivo **lipsum.sh** (como no se puede descargar lo creo con el comando **sudo touch lipsum.sh** y luego lo edito con **sudo nano lipsum.sh** y pego el contenido del archivo. Guardo con **CONTROL + O** y salgo con **CONTROL + X**). Con el comando **nano lipsum.sh** puedo ver el contenido del archivo.
* Genera los 5 archivos txt basándose en el sitio lipsum.com: para esto ejecuto el comando **bash lipsum.sh**).
* Verifica que se crearon los cinco archivos y que tengan contenido: Esto puedo hacerlo con un **ls** para ver los archivos creados y luego usando el comando **nano + nombre del archivo** para ver si tienen contenido.
* Crea un commit con los archivos generados y el lipsum.sh, luego haz un push a tu repositorio en github: **git push -u origin generarlipsum** (Tuve que usar este comando para hacer el primer push ya que si hago **git push** solo no me lo toma ya que la rama está creada en el local pero no en el remoto).
* Codifica un nuevo archivo, "contar.sh", que lea cada uno de los txt generados y luego devuelva por cada archivo, la cantidad de líneas de ese archivo: utilizo **sudo touch contar.sh** para crear el nuevo archivo y pego la solución que es:

```
#!/bin/bash

for file in loremipsum-*.txt
do
    lines=$(wc -l < "$file")
    echo "$file tiene $lines líneas."
done
```

## Explicación a la resolución:
Para lograr esto, podemos utilizar un **ciclo for** para recorrer cada archivo de texto y usar el comando **wc** para contar el número de líneas en cada uno de ellos. Podemos guardar el resultado en una variable y luego imprimirlo en pantalla junto con el nombre del archivo correspondiente.
Aquí está el código para el archivo "contar.sh":

```
#!/bin/bash

for file in loremipsum-*.txt
do
    lines=$(wc -l < "$file")
    echo "$file tiene $lines líneas."
done
```

### Explicación del código:
* La primera línea #!/bin/bash especifica que se está utilizando el intérprete de bash para ejecutar el script.
* El ciclo for recorre cada archivo de texto que cumple con el patrón "loremipsum-*.txt".
* En cada iteración, utilizamos el comando wc con la opción -l para contar el número de líneas en el archivo y lo redireccionamos al archivo correspondiente con la sintaxis "< $file". El resultado se guarda en la variable "lines".
* Finalmente, imprimimos el nombre del archivo y el número de líneas utilizando el comando echo.
* Para ejecutar el script, abrimos una terminal y nos ubicamos en el directorio donde se encuentra el archivo "contar.sh" y los archivos de texto. 
* Luego, ingresamos el comando:
**bash contar.sh**
Esto mostrará en pantalla la cantidad de líneas de cada archivo de texto.
