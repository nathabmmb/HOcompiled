# Respuestas:
## I - Qué esperaba?
	**Paso 1:**
		Que busque los inlude statements e identifique las funciones que están definidas en los header files y/o librerias. También revisa errores clásicos y básicos de sintaxis para no perder tiempo de compilación. El output es un archivo .pp.c	
	
	**Paso 2:**
		Convertir el código de C pre-procesado en código assembler, realizando las optimizaciones apropiadas tanto a nivel de instrucciones como de hardware en general. El output es un archivo .asm

	**Paso 3:**
		Convertir el código assembler en lenguaje de máquina (binario), aunque sin linkear. Por lo que si se utiliza el programa nm se verían algunas entradas "undefined". el output es un "objeto" (un archivo .o)

	**Paso 4:**
		Establece los links entre nuestros binarios y las librerías dinámicas que son necesarias para la ejecución del programa. El output es un archivo ejecutable funcional :D.

## II - Qué agregó el pre-processing?
	850 lineas de comentarios indicando los nombres de las librerías usadas, definiendo tipos (deftypes), estructuras (structs), funciones y demás. 

## III - Identificar las funciones en el código assembler
	Entre las lineas 39-59 parece estar definida la función *add_numbers*, entre las lineas 10-38 parece estar definida la función *main*. Si te digo que entiendo algo más, ciertamente te miento.

## IV - Mencione que significan los símbolos encontrados en el objeto
	"*T add_numbers*" indica que existe una función global llamada "add_numbers";
	"*T main*" indica que existe una función global llamada "main";
	"*U printf*" indica que existe un objeto llamado "printf", pero no conoce el tipo de entrada que es (UNDEFINED). Es necesario realizar el linkeo del objeto para que se "devele" el tipo de entrada.

## V - Indique en que se diferencian los símbolos entre el objeto y el ejecutable
	Para empezar, ahora hay como 40 símbolos (vs 3 en el objeto). Las entradas tienen diferentes "referencias" (los codigos hexadecimales a la izquierda de los descriptores) (no se si eso signfica algo **at all**). 
	La entrada printf ahora aparece como "printf@GLIBC_2.2.5" indicando que durante el runtime hay que llamar a esa libreria para :)
 