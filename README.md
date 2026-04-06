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











