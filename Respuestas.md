NOMBRE: Omar Casanova Antúnez
EXPEDIENTE: 225206862

# Práctica de Logging en Java (`java.util.logging`)

## Actividad guiada 1: comparar System.out y Logger

1. ¿Qué información adicional muestra el mensaje del Logger?
Muestra la fecha y la hora exacta, pues entonces también incluye el nombre de la clase y el método ejecutor, lo cual se complementa indicando el nivel del mensaje.

2. ¿Aparece la fecha/hora?
Sí aparece la fecha y la hora en el registro, lo cual permite ubicar el momento del evento.

3. ¿Aparece el nombre de la clase?
Sí aparece el nombre de la clase, y ahora también se muestra el método asociado.

4. ¿Aparece el nivel del mensaje?
Sí aparece el nivel especificado, pues entonces indica claramente que es INFO.

5. ¿Cuál de los dos mecanismos proporciona más información para diagnosticar un problema?
El Logger proporciona más información, lo cual facilita ubicar el origen exacto del fallo, y ahora se evitan suposiciones innecesarias.

---

## Actividad de aprendizaje: clasificar mensajes

| Situación | Nivel propuesto |
|---|---|
| La aplicación inicia correctamente | INFO |
| No existe el archivo solicitado | SEVERE |
| Se procesaron 250 registros | INFO |
| Se encontró una calificación inválida | WARNING |
| Se cargó `application.properties` | CONFIG |
| Se desea conocer el valor de una variable durante depuración | FINE |
| La aplicación no puede continuar | SEVERE |

---

## Actividad guiada 2: experimentar con niveles

| Configuración | SEVERE | WARNING | INFO | FINE |
|---|---|---|---|---|
| `SEVERE` | Sí | No | No | No |
| `WARNING` | Sí | Sí | No | No |
| `INFO` | Sí | Sí | Sí | No |
| `FINE` | Sí | Sí | Sí | Sí |
| `ALL` | Sí | Sí | Sí | Sí |

---

## Comparación de llamadas con excepciones

`LOG.severe(e.getMessage())` solo imprime el mensaje descriptivo del error, pues entonces `LOG.log(Level.SEVERE, "Error al leer archivo", e)` registra la excepción completa junto con su traza de pila (stack trace), lo cual permite localizar con certeza el método y la línea de código donde surgió la anomalía, y ahora se cuenta con un contexto técnico detallado para resolver el fallo.

---

## Comparación XML vs texto

| Característica | XML | Texto |
|---|----|---|
| Fácil de leer por una persona | No | Sí |
| Fácil de procesar automáticamente | Sí | No |
| Estructura explícita | Sí | No |
| Tamaño más compacto | No | Sí |
| Adecuado para inspección rápida | No | Sí |

---

## Explicación de la diferencia entre Logger, Handler, Level y Formatter

El `Logger` es la puerta de entrada que captura los registros de la aplicación, pues entonces los canaliza hacia los `Handler` configurados, lo cual permite enviar la salida a múltiples destinos como consola o archivo; y ahora, mediante el `Level` se establece el umbral de severidad para descartar mensajes no deseados, mientras que el `Formatter` se encarga de dar la presentación final, pues entonces define si la salida se representará en texto plano o estructura XML.
