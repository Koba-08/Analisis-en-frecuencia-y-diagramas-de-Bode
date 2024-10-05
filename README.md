# Analisis en frecuencia y diagramas de Bode
El análisis en frecuencia es un método para evaluar el comportamiento de sistemas dinámicos mediante la observación de la salida ante cambios en la frecuencia de entrada. Se utilizan señales sinusoidales de la forma $$\( R = A \sin(\omega_k T + \theta) \)$$, asumiendo que el sistema es lineal. Al variar la frecuencia de entrada, se generan cambios en la amplitud y la fase de la señal de salida, lo que permite entender mejor la respuesta del sistema.  

## La representación matemática
de señales sinusoidales es útil porque permite su tratamiento mediante fasores. Los fasores, que representan la señal en términos de amplitud y fase, asumen una frecuencia constante. Al representar tanto la entrada como la salida del sistema como fasores, se facilita el análisis y la representación del comportamiento del sistema en su conjunto, simplificando los cálculos y la comprensión de las interacciones entre las señales.

## funcion de transferencia en terminos de la frecuencia
Para expresar la función de transferencia en términos de la frecuencia, se utiliza la relación entre la variable de Laplace $$\( s \)$$ y la frecuencia $$\( \omega \)$$, donde $$\( s = j\omega \)$$. Además, la equivalencia de mapeo de polos y ceros se puede representar como $$\( z = e^{sT} \)$$. Sustituyendo $$\( s \)$$ por $$\( j\omega \)$$, obtenemos que:

$$\[
z = e^{j\omega T}
\]$$

Esto permite representar la función de transferencia de un sistema en el dominio de la frecuencia, facilitando el análisis de su comportamiento en respuesta a señales sinusoidales.

💡 Ejemplo:
Para expresar la función de transferencia $$\( H(z) \)$$ en el dominio de la frecuencia, comenzamos con la función dada:

$$\[
H(z) = \frac{1}{(z - 0.1)(z - 5)}
\]$$

Con un tiempo de muestreo $$\( T = 0.1 \)$$ seg, sustituimos $$\( z \)$$ por $$\( e^{j\omega T} \)$$:

$$\[
H(e^{j\omega T}) = \frac{1}{(e^{j\omega T} - 0.1)(e^{j\omega T} - 5)}
\]$$

Ahora, utilizando la representación de $$\( e^{j\omega T} \)$$ en términos de funciones trigonométricas:

$$\[
e^{j\omega T} = \cos(\omega T) + j \sin(\omega T)
\]$$

Sustituyendo esto en la función de transferencia:

$$\[
H(e^{j\omega T}) = \frac{1}{(\cos(\omega T) + j \sin(\omega T) - 0.1)(\cos(\omega T) + j \sin(\omega T) - 5)}
\]$$

Ahora, expandimos los términos:

1. *Parte Real:*
  $$\[
   (\cos(\omega T) - 0.1)(\cos(\omega T) - 5) - (\sin(\omega T))^2
   \]$$

2. *Parte Imaginaria:*
   $$\[
   j\left[(\cos(\omega T) - 0.1)\sin(\omega T) + (\cos(\omega T) - 5)\sin(\omega T)\right]
   \]$$

Así, la función de transferencia en el dominio de la frecuencia queda expresada en términos de sus partes real e imaginaria, permitiendo un análisis más detallado del comportamiento del sistema. 

La representación final sería:

$$\[
H(e^{j\omega T}) = \frac{1}{(\text{Parte Real}) + j (\text{Parte Imaginaria})}
\]$$ 

Esto ofrece una forma clara para analizar la respuesta en frecuencia del sistema.


   
## Diagramas de frecuencia

Para cualquier función de transferencia, es posible separar la parte real e imaginaria, lo que permite calcular la magnitud y la fase en el dominio de la frecuencia. Esto es fundamental para analizar el comportamiento del sistema, ya que la magnitud representa la respuesta del sistema a diferentes frecuencias, mientras que la fase indica el desfase entre la entrada y la salida.

Representación Gráfica:

Magnitud y Fase:

La magnitud se puede graficar en función de la frecuencia, usando escalas lineales o logarítmicas (en decibelios).
La fase también se representa en función de la frecuencia, proporcionando información sobre el comportamiento del sistema a diferentes frecuencias.
Coordenadas Polares:

La representación de la magnitud y la fase se puede realizar en coordenadas polares, donde la magnitud se muestra como la distancia desde el origen y la fase como el ángulo respecto al eje real.
Estas representaciones gráficas son útiles para observar y entender el comportamiento dinámico del sistema, facilitando el diseño y ajuste de controladores
Los diagramas de Bode son herramientas gráficas utilizadas para representar la respuesta en frecuencia de sistemas lineales. En ellos, se utiliza la escala en decibelios (dB) para expresar la ganancia y la fase de la función de transferencia.

### Decibelios (dB)

- *Definición*: Los decibelios no son una unidad física, sino una forma de interpolación para expresar cantidades como ganancia o potencia.
- *Fórmula para la Ganancia*: La ganancia en decibelios se calcula con la fórmula:

$$\[
A_{dB} = 20 \log_{10}(A)
\]$$

donde $$\( A \)$$ es la ganancia lineal del sistema. Esta expresión indica que una ganancia de $$\( A = 1 \) (0 dB)$$ significa que no hay amplificación, mientras que ganancias mayores o menores se reflejan en valores positivos o negativos en dB.

### Diagramas de Bode

Los diagramas de Bode consisten en dos gráficas:
1. *Diagrama de Magnitud*: Representa la ganancia en dB frente a la frecuencia (en una escala logarítmica).
2. *Diagrama de Fase*: Muestra el desfase en grados también en función de la frecuencia.

Estos diagramas permiten visualizar cómo responde un sistema a diferentes frecuencias, facilitando el análisis y diseño de sistemas de control.

### Diagramas polar

El diagrama polar es una representación gráfica que muestra la relación entre la magnitud y la fase de una función de transferencia en el dominio de la frecuencia. Este tipo de diagrama es especialmente útil para analizar sistemas lineales, ya que permite visualizar cómo responden ante diferentes frecuencias.

## Efecto de parámetros dinámicos
### Análisis Frecuencial en Tiempo Discreto

El análisis en frecuencia en sistemas de tiempo discreto no se puede realizar de manera directa como en el caso de los sistemas continuos. Sin embargo, se puede utilizar la transformación bilineal (también conocida como transformación de Tustin) para aproximar el análisis de frecuencia en tiempo discreto a uno en tiempo continuo.

La transformación bilineal se expresa como:

$$\[
w = \frac{2}{T} \frac{z - 1}{z + 1}
\]$$

se puede reescribir $$\( z \)$$ en términos de $$\( w \)$$ como:

$$\[
z = \frac{1 + \frac{wT}{2}}{1 - \frac{wT}{2}}
\]$$

#### Sustitución para Frecuencia

Al sustituir $$\( z \)$$ por $$\( e^{j\omega T} \)$$, obtenemos:

$$\[
w = j\frac{2}{T} \tan\left(\frac{\omega T}{2}\right)
\]$$


Sustituyendo $$\( w = jv \)$$, resulta en:

$$\[
v = \frac{2\omega T}{2} \tan\left(\frac{\omega T}{2}\right)
\]$$

💡 Ejemplo

### Ejemplo de Análisis Frecuencial

1. *Dominio Continuo:*

   $$\[
   G_s = \frac{1}{s + 10}
   \]$$
   
   Esta función representa un sistema de primer orden, donde el polo está en $$\( s = -10 \)$$.

3. *Dominio Discreto:*

   $$\[
   G_z = \frac{0.06321}{z - 0.3679}
   \]$$
   
   Aquí, el sistema tiene un cero en $$\( z = 0.06321 \)$$ y un polo en $$\( z = 0.3679 \)$$. Esto es un ejemplo de un filtro discreto.

4. *Dominio de Frecuencia:*

   $$\[
   G_w = \frac{0.924 - 0.05w + 1}{w + 9.242}
   \]$$
   
   En esta función, $$\( w \)$$ es la variable de frecuencia que se relaciona con $$\( z \)$$ y $$\( s \)$$ a través de las transformaciones adecuadas.
aparece un cero que no tenia; la ganancia y el polo estan ubicados aproximadamente igual al sistema continuo

### Respuesta Temporal vs. Respuesta en Frecuencia

La respuesta temporal y la respuesta en frecuencia son dos enfoques complementarios para analizar el comportamiento de sistemas en control, especialmente en sistemas en lazo cerrado.


En un sistema en lazo cerrado:

$$\[
G_o = \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}
\]$$

donde:
- $$\( \omega_n \)$$ es la frecuencia natural,
- $$\( \zeta \)$$ es el coeficiente de amortiguamiento.


1. *Cálculo del Coeficiente de Amortiguamiento $$(\( \zeta \))$$*:
   $$\zeta = \sqrt{\frac{\ln{Mp}^{2}}{\pi ^{2}+\ln{Mp}^{2}}}$$

2. *Cálculo del Pico Resonante $$(\( M_r \))$$*:
   $$Mr= \frac{1}{2\sqrt{\frac{\ln{Mp}^{2}}{\pi ^{2}+\ln{Mp}^{2}}}\sqrt{1-\frac{\ln{Mp}^{2}}{\pi ^{2}+\ln{Mp}^{2}}}}$$





# Ejercicios

📚 Ejercicio 1:

### Ejercicio 1:Coeficiente de Amortiguamiento

Dado un sistema de segundo orden con una respuesta temporal que presenta un overshoot máximo $$\( M_p = 1.5 \)$$. Calcula el coeficiente de amortiguamiento $$\( \zeta \)$$.

*Solución:*
Utilizamos la fórmula para el coeficiente de amortiguamiento:

$$\zeta = \sqrt{\frac{\ln{Mp}^{2}}{\pi ^{2}+\ln{Mp}^{2}}}$$

Calculamos $$\( \ln^2(1.5) \)$$:
   $$\[
   \ln^2(1.5) \approx (0.4055)^2 \approx 0.1644
   \]$$

Sustituyendo en la fórmula:
   $$\[
   \zeta = \frac{0.1644}{\pi^2 + 0.1644}
   \]$$
   Donde $$\( \pi^2 \approx 9.8696 \)$$.

 Entonces:
   $$\[
   \zeta = \frac{0.1644}{9.8696 + 0.1644} \approx 0.0163
   \]$$

   $$\sqrt{0.0163}\approx 0.127\$$

*Resultado:*
El coeficiente de amortiguamiento $$\( \zeta \approx 0.127 \)$$.



📚Ejercicio 2:

### Ejercicio 2: Magnitud y Fase en el Dominio de Frecuencia

Considera un sistema con la siguiente función de transferencia en lazo abierto:

$$\[
G(s) = \frac{1}{s^2 + 10s + 25}
\]$$

Calcula la magnitud y la fase de la respuesta en frecuencia a una frecuencia $$\( \omega = 5 \)$$ rad/s.

*Solución:*

1. *Sustitución de \( s \)*:
   Usamos \( s = j\omega \):
   $$\[
   G(j5) = \frac{1}{(j5)^2 + 10(j5) + 25}
   \]$$
   Calculamos:
   $$\[
   G(j5) = \frac{1}{-25 + 50j + 25} = \frac{1}{50j}
   \]$$

2. *Magnitud*:
   $$\[
   |G(j5)| = \left|\frac{1}{50j}\right| = \frac{1}{50}
   \]$$

3. *Fase*:
   La fase de $$\( G(j5) \)$$ es:
   $$\[
   \angle G(j5) = \angle\left(\frac{1}{50} e^{-j\frac{\pi}{2}}\right) = -90^\circ
   \]$$

*Resultado:*
La magnitud es $$\( |G(j5)| = 0.02 \) y la fase es \( -90^\circ \)$$.



## Conclusiones

El análisis de sistemas de control integra la respuesta temporal y en frecuencia, donde el overshoot y el coeficiente de amortiguamiento son cruciales para evaluar la estabilidad. Herramientas como la transformación bilineal y los diagramas de Bode permiten visualizar y diseñar sistemas de manera efectiva. Comprender estas relaciones es esencial para asegurar un rendimiento óptimo y estable en aplicaciones de control.
