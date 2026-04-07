# Unidad 2 Graficación2D
**Temario:**

**2.1. Transformación bidimensional.**

  2.1.1. Traslación.

  2.1.2. Escalamiento.

  2.1.3. Rotación.

  2.1.4. Sesgado.

**2.2.Representación matricial de las transformaciones bidimensionales.**

**2.3. Trazo de líneas curvas.**

   2.3.1. Bézier.

   2.3.2. B-spline.

**2.4. Fractales.**

**2.5. Uso y creación de fuentes de texto.**

# Introducción
En el ámbito de la computación gráfica, las transformaciones bidimensionales y el manejo de elementos visuales son fundamentales para el desarrollo de aplicaciones interactivas, animaciones y sistemas de diseño digital. A través de este temario, se abordarán los conceptos esenciales que permiten manipular objetos en un plano, tales como la traslación, el escalamiento, la rotación y el sesgado, los cuales constituyen la base para modificar la posición, tamaño y orientación de figuras.

Asimismo, se estudiará la representación matricial de estas transformaciones, herramienta clave para aplicar múltiples cambios de forma eficiente, incluyendo su implementación práctica mediante el control con teclas de dirección. Posteriormente, se explorará el trazo de líneas curvas, destacando métodos como las curvas de Bézier y B-spline, ampliamente utilizadas en animación y diseño gráfico, acompañadas de ejercicios aplicados para reforzar su comprensión.

De igual manera, se introducirá el concepto de fractales, estructuras geométricas complejas que permiten generar figuras detalladas a partir de patrones repetitivos. Finalmente, se analizará el uso y la creación de fuentes de texto, elemento esencial en la presentación visual de la información dentro de sistemas gráficos.

En conjunto, estos temas proporcionan las bases necesarias para comprender y desarrollar representaciones visuales dinámicas y eficientes en entornos digitales.

# 2.1. Transformación bidimensional.

Las transformaciones bidimensionales son operaciones matemáticas que permiten modificar la posición, tamaño, orientación o forma de un objeto dentro de un plano (ejes X y Y). Estas transformaciones son fundamentales en áreas como la animación, videojuegos, diseño gráfico y modelado en software como Blender.

En un entorno práctico, como Blender, aunque se trabaja en 3D, estas transformaciones pueden aplicarse sobre un plano o en dos ejes, lo que permite entender fácilmente su funcionamiento.

## 2.1.1. Traslación.

La traslación consiste en mover un objeto de una posición a otra sin alterar su forma, tamaño u orientación.

Se realiza desplazando el objeto en los ejes X y/o Y.
Matemáticamente, se suma un valor a las coordenadas del objeto.

**Ejemplo en Blender:**

+ Selecciona un objeto (por ejemplo, un cubo).
+ Presiona la tecla G (Grab/Mover).
+ Luego presiona X o Y para moverlo en un eje específico.
+ Mueve el objeto y confirma con clic.

**Ejemplo práctico:**
Mover un objeto hacia la derecha o hacia arriba en la escena.


<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/4807c0f6-4036-43fa-b070-62382afb4529" />

## 2.1.2 Escalamiento

**_Movimiento de Escalamiento (Scaling)_**

El escalamiento es la transformación que permite cambiar el tamaño de un objeto. Esto significa que el objeto puede hacerse más grande o más pequeño, pero sin cambiar su forma original (si el escalado es uniforme).

__¿Cómo funciona?__

Cada punto del objeto se multiplica por un valor llamado factor de escala:

+ Si el valor es mayor que 1 → el objeto crece
+ Si el valor es entre 0 y 1 → el objeto se reduce
+ Si es negativo → el objeto se invierte (como un espejo)

__Tipos de escalamieneto__

__1. Punto de referencia (origen o pivote)__

El escalamiento siempre ocurre respecto a un punto, llamado pivote.

Si escalas desde el centro, el objeto crece hacia todos lados
Si escalas desde una esquina, el objeto parecerá moverse

🧸 En Blender:
Puedes cambiar el pivote (centro, cursor 3D, elemento activo)

🧸 Para exposición:
“El punto de referencia determina desde dónde crece o se reduce el objeto.”

__2.  Escalamiento uniforme vs no uniforme__
+ Uniforme: mismo valor en todos los ejes → no se deforma
+ No uniforme: valores diferentes → el objeto se estira o aplasta

🧸 Ejemplo:

+ Uniforme: un círculo sigue siendo círculo
+ No uniforme: un círculo se vuelve óvalo

🧸 En Blender:

+ S → uniforme
+ S + X o Y → no uniforme

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e35c5b97-05f5-4539-8f62-65759cda659c" />

## 2.1.3. Rotación.

La rotación es una transformación bidimensional que permite girar un objeto alrededor de un punto fijo, conocido como centro de rotación o pivote. Esta operación modifica la orientación del objeto dentro del plano, pero no altera su forma ni su tamaño, lo que la convierte en una transformación rígida.

__¿Cómo funciona la rotación?__

Cuando un objeto rota, cada uno de sus puntos se desplaza describiendo un arco circular alrededor del punto de rotación. Es decir, todos los puntos mantienen la misma distancia respecto al centro, pero cambian su posición angular.

_La rotación se define principalmente por tres elementos:_

+ Ángulo de rotación: cantidad de giro que se aplica al objeto
+ Sentido de rotación: puede ser
   + Horario (en dirección de las manecillas del reloj)
   + Antihorario (en sentido contrario)
+ Punto de rotación (pivote): lugar desde donde gira el objeto

**Importancia del punto de rotación**

El resultado visual de una rotación depende mucho del pivote:

+ Si el pivote está en el centro del objeto, este gira sobre sí mismo
+ Si el pivote está fuera del objeto, parecerá que el objeto “orbita” alrededor de ese punto

🧸 Esto es muy importante en animación, ya que permite simular movimientos reales como ruedas, brazos o puertas.

**Medición del ángulo**

La rotación se mide normalmente en grados (°):

- 0° → sin cambio
- 90° → cuarto de vuelta
- 180° → media vuelta
- 360° → vuelta completa

También puede medirse en radianes en contextos matemáticos.

<img width="501" height="503" alt="image" src="https://github.com/user-attachments/assets/0139cfa4-7f67-45af-83e8-cf327eff80af" />

**Ejemplo en Blender**

Para aplicar una rotación en Blender:

+ Selecciona el objeto
+ Presiona la tecla R (Rotate)
+ Presiona X, Y o Z para elegir el eje de rotación
+ Mueve el mouse para girar el objeto
+ Haz clic o presiona Enter para confirmar

🧸 También puedes escribir un valor numérico (por ejemplo: R → Z → 90) para mayor precisión.

## 2.1.4. Sesgado.

El sesgado es una transformación bidimensional que consiste en inclinar o deformar un objeto, desplazando sus puntos en una dirección específica. A diferencia del escalamiento o la rotación, el sesgado sí altera la forma del objeto, aunque generalmente mantiene su área.

__¿Cómo funciona el sesgado?__

En el sesgado, los puntos del objeto se desplazan de manera proporcional a su posición respecto a un eje.

- Un eje se mantiene “fijo”
+ El otro eje se desplaza progresivamente
- Esto genera una inclinación

🧸 Es como si “empujaras” la parte superior de un objeto hacia un lado mientras la base permanece en su lugar.

__Tipos de Sesgado__

El sesgado puede aplicarse en diferentes direcciones dependiendo del eje que se tome como referencia. Los dos tipos principales son el sesgado en X y el sesgado en Y, y cada uno produce una deformación distinta en el objeto.

**Sesgado en X (Shear en X)**

El sesgado en X consiste en desplazar los puntos del objeto en dirección horizontal (eje X), mientras que su posición vertical (eje Y) se mantiene igual.

__¿Cómo funciona?__
+ Cada punto del objeto se mueve hacia la derecha o izquierda
+ El desplazamiento depende de su posición en Y
+ Los puntos más “altos” o más “bajos” se mueven más o menos

🧸 Es decir, el objeto se “inclina” hacia un lado.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/884fa215-af7f-478f-8370-ea9eb8e60190" />


# 2.2.Representación matricial de las transformaciones bidimensionales.

En computación gráfica, las transformaciones bidimensionales como la traslación, escalamiento, rotación y sesgado pueden representarse mediante matrices. Esto permite aplicar operaciones de forma más organizada, rápida y precisa, especialmente cuando se trabajan múltiples transformaciones sobre un mismo objeto.

Una matriz es una forma de organizar números en filas y columnas, y se utiliza para transformar las coordenadas de un punto. Si un punto en el plano se representa como:

P(x,y)

Se puede escribir como un vector:

<img width="40" height="40" alt="image" src="https://github.com/user-attachments/assets/0e2b2158-4396-4d1c-9cee-e9d088f837ba" />

Al multiplicar este vector por una matriz, obtenemos una nueva posición transformada.

__1. Matriz de Traslación__

La traslación mueve un objeto en el plano. Para representarla con matrices se utiliza una forma extendida llamada coordenadas homogéneas:

<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/bbb1e88a-478f-4cbc-8c84-fbd530a4ad9b" />

Donde:

+ Tx es el desplazamiento en X
+ Ty es el desplazamiento en Y

Esto permite mover un punto sin cambiar su forma.

__2. Matriz de Escalamiento__

El escalamiento cambia el tamaño del objeto. Su matriz es:

<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/8677e4bc-da84-4b85-8284-e33de518bc3c" />

Donde:

+ Sx es el factor de escala en X
+ Sy es el factor de escala en Y

Si ambos valores son iguales, el escalamiento es uniforme.

__3. Matriz de Rotación__

La rotación gira el objeto un ángulo θ:

<img width="205" height="203" alt="image" src="https://github.com/user-attachments/assets/6a9a7042-41ed-43c7-92b2-2a2bcc093565" />

Donde:

+ θ es el ángulo de rotación
+ Se usan funciones trigonométricas

Esta matriz rota el objeto alrededor del origen (0,0).


__4. Matriz de Sesgado__

El sesgado deforma el objeto inclinándolo. Existen dos formas:

🧸 Sesgado en X:

<img width="257" height="208" alt="image" src="https://github.com/user-attachments/assets/c226fc31-4037-419e-b0cb-b3f135f5a977" />

Donde:

+ Shx es el factor de inclinación horizontal

🧸 Sesgado en Y:

<img width="262" height="208" alt="image" src="https://github.com/user-attachments/assets/8cefb159-38e9-4951-9941-6ae7de42f1ab" />

Donde:

+ Shy es el factor de inclinación vertical

**🍁Importancia de la representación matricial**

El uso de matrices permite:

+ Aplicar múltiples transformaciones fácilmente
+ Combinar varias operaciones en una sola
+ Optimizar cálculos en gráficos y animaciones
+ Implementar estas transformaciones en software como Blender, videojuegos o simulaciones


Para poner esto en práctica, se realiza un ejemplo en Blender en el cual se controla el movimiento de un dibujo utilizando las teclas del teclado.

<img width="502" height="503" alt="image" src="https://github.com/user-attachments/assets/c5990d95-e746-4c01-b3ea-80efb62137a2" />

# 2.3 Trazo de líneas curvas

El trazo de líneas curvas es un elemento fundamental en la computación gráfica, ya que permite representar formas suaves, naturales y complejas que no pueden lograrse únicamente con líneas rectas. A diferencia de los segmentos lineales, las curvas permiten modelar objetos más realistas, como trayectorias de movimiento, contornos de figuras, animaciones y diseños gráficos.

Las curvas se construyen a partir de puntos de control y funciones matemáticas que determinan su forma. Entre los métodos más utilizados para generar curvas están las curvas de Bézier y las curvas B-spline, las cuales ofrecen gran flexibilidad y precisión en el diseño.


## 2.3.1 Curvas de Bézier

Las curvas de Bézier son uno de los métodos más utilizados para generar curvas suaves en gráficos por computadora. Se definen mediante un conjunto de puntos de control, los cuales determinan la forma de la curva.

__🧸 ¿Cómo funcionan?__

Una curva de Bézier no necesariamente pasa por todos sus puntos de control, sino que estos actúan como “imanes” que atraen la curva y definen su dirección. La curva siempre comienza en el primer punto de control y termina en el último.

Dependiendo del número de puntos, existen diferentes tipos:

+ Lineal (2 puntos)
+ Cuadrática (3 puntos)
+ Cúbica (4 puntos, la más común)

<img width="227" height="222" alt="image" src="https://github.com/user-attachments/assets/3574b5de-14c4-4d77-b4e2-7275fccd6b69" />

__🧸 Características__
+ Son fáciles de controlar, ya que dependen de pocos puntos de control, lo que permite crear formas complejas de manera sencilla y sin necesidad de cálculos complicados.
+ Generan curvas suaves y continuas, evitando cambios bruscos en la dirección, lo que las hace ideales para representar formas naturales y visualmente agradables.
+ Permiten modificar la forma moviendo los puntos de control o sus manejadores, lo que facilita hacer ajustes rápidos sin tener que redibujar toda la curva.
+ Su comportamiento es predecible, lo que ayuda a obtener resultados precisos al momento de diseñar o ajustar una curva.
+ Son muy utilizadas en diseño gráfico y animación, especialmente en la creación de logotipos, tipografías, ilustraciones y trayectorias de movimiento.
+ Requieren pocos recursos computacionales, lo que las hace eficientes para trabajar en aplicaciones digitales y en tiempo real.

<img width="591" height="505" alt="image" src="https://github.com/user-attachments/assets/3bcf615c-873d-4fc0-a4c7-8d328a407533" />

##  2.3.2. B-spline

Las curvas B-spline son una extensión de las curvas de Bézier, pero ofrecen mayor control y flexibilidad, especialmente cuando se trabaja con muchas curvas o formas complejas.

__🧸 ¿Cómo funcionan?__

Las B-spline también utilizan puntos de control, pero a diferencia de las Bézier:

+ La curva no necesariamente pasa por los puntos extremos
+ Cada segmento de la curva depende solo de algunos puntos cercanos
+ Esto permite modificar partes de la curva sin afectar toda la forma

__🧸 Características de las curvas B-spline__

+ **Mayor suavidad en la curva:** Las curvas B-spline se caracterizan por generar formas mucho más suaves y continuas en comparación con otros métodos. Esto se debe a que están construidas por varios segmentos que se unen de manera gradual, evitando cambios bruscos en la dirección. Gracias a esto, son ideales para representar superficies orgánicas o formas naturales, como cuerpos, objetos redondeados o trayectorias fluidas en animación.
+ **Mejor control local:** Una de sus ventajas más importantes es el control local. Esto significa que al mover un punto de control, solo se modifica una parte específica de la curva y no toda la figura completa. Esto permite trabajar con mayor precisión, ya que se pueden hacer ajustes pequeños sin afectar el resto del diseño, lo cual es muy útil en modelado detallado.
+ **Ideales para diseños complejos:** Las B-spline son especialmente útiles cuando se trabaja con figuras complejas que requieren muchos puntos de control. A diferencia de otras curvas, permiten manejar gran cantidad de puntos sin perder estabilidad en la forma. Esto las hace muy utilizadas en áreas como el diseño industrial, modelado 3D y animación avanzada, donde se necesitan curvas detalladas y bien definidas.
+ **No se deforman completamente al mover un solo punto:** A diferencia de las curvas de Bézier, donde un solo punto puede alterar toda la curva, en las B-spline el efecto de cada punto está limitado a una región cercana. Esto evita deformaciones drásticas y hace que la curva sea más estable. Gracias a esto, el diseñador tiene mayor control y puede realizar cambios sin arruinar el trabajo previo.

<img width="560" height="520" alt="image" src="https://github.com/user-attachments/assets/ff62b7b5-30d8-4f52-a684-4808651491d7" />


Ejemplo con blender: 
Animación con huesos: 

__Sin vista de heusos:__

https://github.com/user-attachments/assets/2ecc5e32-0cad-496b-b8d6-ae93b43ad331

__Vista cin huesos:__

https://github.com/user-attachments/assets/6cc9d69d-be33-4db7-9d49-1e04b3dbaebb

# 2.4. Fractales

Los fractales son estructuras geométricas que se caracterizan por tener formas complejas que se repiten a diferentes escalas. Esto significa que, si se observa una parte pequeña de un fractal, esta tendrá una forma similar al todo, propiedad conocida como autosimilitud.

A diferencia de las figuras geométricas tradicionales (como cuadrados o círculos), los fractales no tienen una forma simple, sino que están formados por patrones que se repiten infinitamente, generando figuras muy detalladas y, en muchos casos, de gran belleza visual.

__🧸 ¿Cómo se generan los fractales?__

Los fractales se crean a partir de procesos iterativos, es decir, repitiendo una misma operación matemática varias veces. En cada iteración, el patrón se vuelve más complejo y detallado.

**🧸 Por ejemplo:**
Se comienza con una figura básica y se le aplica una transformación una y otra vez, generando nuevas formas a partir de la original.

__🧸 Características principales__
+ **Autosimilitud:** las partes pequeñas se parecen a la figura completa
+ **Detalle infinito:** mientras más se acerca (zoom), más detalles aparecen
+ **Generación iterativa:**  se crean repitiendo un proceso
+ **Formas irregulares:** no siguen la geometría tradicional

__🧸 Aplicaciones de los fractales__

Los fractales tienen múltiples usos en diferentes áreas:

+ Gráficos por computadora: creación de paisajes, montañas, nubes
+ Animación y videojuegos: generación de escenarios realistas
+ Arte digital: diseños abstractos y visualmente atractivos
+ Ciencia: modelado de fenómenos naturales como costas, plantas o sistemas biológicos

<img width="851" height="302" alt="image" src="https://github.com/user-attachments/assets/46694d2e-c875-4c39-8dad-df4a13975cde" />

# 2.5 Uso y creación de fuentes de texto

Las fuentes de texto (tipografías) son un elemento fundamental en la representación visual de la información, ya que permiten comunicar ideas de manera clara, organizada y estética. En computación gráfica, el uso adecuado de fuentes influye directamente en la legibilidad, el diseño y la experiencia del usuario.

Además de utilizar fuentes existentes, también es posible crear nuevas tipografías, lo que resulta importante en áreas como el diseño gráfico, la identidad visual y el desarrollo de interfaces.
Uso de fuentes de texto

__🧸 Uso de fuentes de texto__

El uso de fuentes consiste en seleccionar y aplicar un tipo de letra adecuado según el contexto en el que se presenta la información.

__🍁  Importancia del uso correcto__

Elegir una fuente adecuada permite:

+ Mejorar la legibilidad del texto
+ Transmitir una emoción o estilo (formal, moderno, creativo, etc.)
+ Organizar la información visualmente
+ Facilitar la comprensión del contenido

__🧸 Tipos de fuentes__

Existen diferentes tipos de fuentes, cada una con características específicas:

+ **Serif:** tienen pequeños adornos (ej. Times New Roman), se usan en textos formales
+ **Sans serif:** no tienen adornos (ej. Arial), son más modernas y limpias
+ **Decorativas:** diseños llamativos, se usan en títulos o diseños creativos
+ **Monoespaciadas:** todos los caracteres ocupan el mismo espacio (usadas en programación)

<img width="850" height="280" alt="image" src="https://github.com/user-attachments/assets/14a2a8cd-a2c0-4f41-9c7c-6e1c3ccd2a24" />


__🧸 Propiedades de las fuentes__

Las fuentes pueden modificarse mediante diferentes atributos:

+ Tamaño
+ Color
+ Grosor (negrita)
+ Estilo (cursiva)
+ Espaciado entre letras y líneas

Estas propiedades ayudan a mejorar la presentación del texto.


# Conclusión

El estudio de las transformaciones bidimensionales permite comprender cómo los objetos pueden ser modificados dentro de un plano mediante operaciones como la traslación, el escalamiento, la rotación y el sesgado, las cuales son fundamentales para manipular posición, tamaño, orientación y forma. Estas transformaciones, al ser representadas mediante matrices, facilitan su aplicación de manera más eficiente y precisa, especialmente en el desarrollo de gráficos por computadora y animaciones.

Por otro lado, el trazo de líneas curvas mediante métodos como las curvas de Bézier y B-spline permite generar formas suaves y complejas, siendo esenciales en el diseño gráfico, modelado y animación. Asimismo, el uso de fractales demuestra cómo a partir de patrones simples se pueden crear estructuras visuales altamente detalladas y realistas, incluso presentes en la naturaleza.

Finalmente, el uso y la creación de fuentes de texto resaltan la importancia de la tipografía en la comunicación visual, ya que influyen directamente en la legibilidad y estética de la información. En conjunto, todos estos temas proporcionan una base sólida para el desarrollo de aplicaciones gráficas, permitiendo crear representaciones visuales más dinámicas, precisas y atractivas en distintos entornos digitales.

# Bibliografías
+ TAI. (2022, junio 1). Los tipos de tipografía: características y elección. TAI ARTS. https://taiarts.com/blog/tipos-de-tipografia-caracteristicas-y-eleccion/
+ (S/f). Quora.com. Recuperado el 7 de abril de 2026, de https://www.quora.com/What-is-the-difference-between-a-serif-font-a-sans-serif-font-and-a-script-font
+ Hernández, C. (2023, abril 3). » Clasificación y tipos de tipografías •. Brandcrops. https://brandcrops.com/blog/tipos-tipografias/
+ De, E. (2017, enero 30). Traslación. Enciclopedia Significados. https://www.significados.com/traslacion/
+ IBM Integration Designer. (2021, marzo 3). Ibm.com. https://www.ibm.com/docs/es/integration-designer/8.5.5?topic=tasks-escalations
+ - YouTube. (s/f). Youtu.Be. Recuperado el 7 de abril de 2026, de https://youtu.be/kXwJOefEjJs?si=DHjhgW2g3XTzs0qH
+ (S/f-b). Mathworks.com. Recuperado el 7 de abril de 2026, de https://la.mathworks.com/help/images/matrix-representation-of-geometric-transformations.html
+ 2.2 representacion matricial de transformacion bidimencional. (s/f). Prezi.com. Recuperado el 7 de abril de 2026, de https://prezi.com/qvfu88rnk5hm/22-representacion-matricial-de-transformacion-bidimencional/
+ Fractales. (s/f). Webs.um.es. Recuperado el 7 de abril de 2026, de https://webs.um.es/jmz/DiseGrafSimula/alumnos_08_09/german_ros/index.files/fractal1_Intro%201.html
+ Client challenge. (s/f). Scribd.com. Recuperado el 7 de abril de 2026, de https://es.scribd.com/document/340571254/Uso-y-Creacion-de-Fuentes-de-Texto








