### 1. Transmision de datos: Cómo viaja la información.

La información digital puede enviarse mediante dos modalidades principales: **transmisión en paralelo** o **transmisión en serie**.
* **Transmisión en paralelo:** Permite un flujo de bits garantizado por varios canales. Es típica del sistema de conducciones internas del ordenador y asegura una mayor velocidad.
* **Transmisión en serie:** Es la más extendida para comunicaciones entre dispositivos y periféricos. Aprovecha el envío secuencial de bits que, al ser más lento, precisa menos **ficheros** (menor coste), y está menos sometido a interferencias y errores de transmisión. 

![Transmisión paralelo y serie](/imgs/imgTransmision.jpg)

### 2. Compresión de datos y eficiencia: Cómo optimizar el espacio.

Para enviar o almacenar datos de forma eficiente se utiliza la **codificación de Huffman**, el algoritmo desarrollado en 1952 por David A. Huffman, que es un algoritmo de compresión sin pérdida (*lossless*) que organiza los símbolos en un árbol binario según su freciencia de aparición. Esto da lugar a diferentes ficheros, que presentamos en la siguiente tabla:

|Tipo|Ejemplos|
|---|---|
|**Sin pérdida** (lossless)|`ZIP`, `RAR`, `7z`, `PNG`, `GIF`, `TIFF`, `FLAC`|
|**Con pérdida** (lossy)|`JPEG`, `MP3`, `MPEG`|
|**Sin compresión**|`TXT`, `PDF`|

![Arbol binario](/imgs/imgArbol.jpg)

Aquí tenemos un típico árbol binario que muestra una "codificación de Huffman". En el ejemplo, la frase "*this is an example of a human tree*" está ordenada en base al número de veces que aparece cada caracter, poniendo en parejas de hijos las de menor frecuencia cuyo progenitor esté ordenado como suma de sus hijos. Se podrá decodificar asignando a cada nodo un bit y a las letras valores iguales a 1, 2, 3, 4 o 5 bits según el orden.

### 3. Detección y Corrección de Errores: Cómo garantizar la integridad.

Durante la transmisión pueden ocurrir interferencias. Por ello, para evitar la corrupción de datos se utilizan mecanismos de control:
* **Bits de paridad:** Un bit adicional que indica si el número de '1's es par o impar; permite detectar errores impares, pero no corregirlos.
    > **Inconveniente**:
    > El bit de paridad solo detecta un número **impar** de errores. Si las interferencias invierten dos bits simultáneamente, el error pasa desapercibido y el sistema no puede corregirlo

    En el siguiente archivo se muestra un ejemplo sencillo en Python que ilustra la idea de verificación de paridad par en una cadena de bits:

    [Ejemplo verificación de paridad par en Python](paridad.md)

* **Código de Hamming:** Desarrollado en 1950 por Richard Hamming, distribuye bits de paridad en posiciones correspondientes a potencias de 2, lo que permite no solo detectar el error, sino localizar la posición exacta del bit equivocado y corregirlo.

    #### Como detecta y corrige un bit alterado:
    1. Calcula los bits de paridad en el extremo emisor y los distribuye en posiciones de potencias de 2. 
    2. Se recibe la secuencia en el extremo receptor tras su paso por el canal. 
    3. Recalcula las comprobaciones de paridad e identifica el síndrome de error. 
    4. Localiza la posición exacta del bit erróneo e invierte su valor binario.

    #### Ejemplo detección y corrección de errores:
    * Secuencia enviada: 
    > 1 0 1 0 1 1 1 
    * Secuencia recibida con ruido: 
    > 1 0 1 0 ~~-0-~~ 1 1 (error detectado en la posición 5). 
    * Secuencia corregida por Hamming: 
    > 1 0 1 0 **1** 1 1.

