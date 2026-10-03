# Teoría de la información

## ¿Qué es la información?

En sentido amplio, la **información** es todo aquello que reduce la *incertidumbre*. Cuando se codifica, puede convertirse en una serie de datos que se pueden comunicar y procesar automáticamente. La información **digital** se representa de forma discreta, mientras que las señales *analógicas* son continuas y pueden convertirse en digitales mediante un proceso de codificación. Estos conceptos son fundamentales para comprender cómo se almacena, transmite y comprime la información.

Si se codifica, constituye una serie de **datos** que se pueden comunicar,
una operación que adapta la información al procesamiento automático.

El dato informático es **digital** (o discreto) y, debidamente codificadas,
las señales **analógicas** o continuas se pueden convertir en digitales.

La **teoría de la información**, nacida en 1948 gracias a **Claude Shannon**,
es una disciplina basada en las matemáticas que estudia los fenómenos
relativos a la compresión y transmisión de datos informáticos.

## Entropía

La entropía se puede expresar mediante:

```math
H = -\sum_{i=1}^{n} p_i \log p_i
```

La redundancia es todo lo que no es absolutamente necesario,
aunque habitualmente otorga flexibilidad y fiabilidad.

La redundancia puede eliminarse mediante la **compresión**.

Existen dos tipos principales de compresión.

**Lossy:** compresión con pérdida de información.

**Lossless:** compresión sin pérdida de información.

## Ejemplo de compresión

Cadena original:

`1188888118888811888881188888118888881188888`

Cadena comprimida:

`128512851285128512851285`

Este tipo de representación puede indicar primero el carácter y luego
el número de apariciones consecutivas.

## Compresión y extracción

**Compresión →** reduce el tamaño que ocupa un archivo.

**Extracción →** recupera los datos desde el archivo comprimido.

Los algoritmos de compresión permiten que los archivos ocupen menos
memoria y requieran menos ancho de banda durante su transmisión.

## Tipos de compresión

| Tipo | ¿Pierde información? | Ejemplo |
|---|---|---|
| Lossy | Sí | JPEG, MP3 |
| Lossless | No | PNG, FLAC |

## Proceso de tratamiento de la información

- [x] Codificar
- [x] Comprimir
- [ ] Transmitir
- [ ] Recuperar

## Idea clave

> La información es todo aquello que reduce la incertidumbre.

## Aclaración sobre la compresión

~~La compresión siempre elimina información.~~

Esto no ocurre en la compresión Lossless, ya que permite recuperar la información original.

## Conceptos clave

Algunos conceptos fundamentales son `Lossy`, `Lossless`, `Entropía`, `Redundancia`, `Compresión`, `Extracción` e `Información`.

---

## Más información

Para ver más información puedes consultar el siguiente vídeo [Teoría de Shannon](https://www.youtube.com/watch?v=4ic-J79O9hg).