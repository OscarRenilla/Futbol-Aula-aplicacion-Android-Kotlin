# Fútbol Aula - Práctica final de Móviles (1.ª evaluación)

Aplicación Android en **Kotlin** para gestionar un catálogo de futbolistas, desarrollada como práctica final de la asignatura de Programación Multimedia y Dispositivos Móviles.

El repositorio contiene **dos versiones del mismo proyecto**: el material original entregado por el centro y la solución.

## Estructura

```
.
├── original-plantilla/    # Proyecto base: los 16 ejercicios E01–E16 con TODO sin resolver
├── resuelto/    # Proyecto con los 16 ejercicios implementados
└── README.md
```


## Qué se pide

La app ya trae la interfaz y la infraestructura (base de datos SQLite, sensores, audio, imagen, Bluetooth). El trabajo consiste en completar **16 funciones evaluables** (`app/src/main/java/es/aula/futbol/evaluables/`), cada una con su ejemplo resuelto (`ejemplos/X00`) y sus tests (`E00Test`), así como un ``.md`` para cada uno en ``docs/``.

| Ejercicio | Tema | Qué valida / resuelve |
|---|---|---|
| E01 | Más equipos reales | Lote no vacío, un solo club, posición admitida, fuente HTTPS, sin IDs ni jugadores duplicados |
| E02 | Buscar, filtrar y ordenar | Texto sin tildes/mayúsculas, club, posición, favoritos y orden asc/desc |
| E03 | Etiquetas y valoración | Máx. 5 etiquetas únicas de hasta 24 caracteres; valoración 0–5; conserva nota y favorito |
| E04 | Comparar fichas | De 2 a 4 jugadores distintos; solo datos reales, sin ganador |
| E05 | Sorpresa con sensor | Elige solo entre candidatos visibles; índice circular; vacío -> `null` |
| E06 | Filtro de contraste | Valor finito entre 0 y 3 -> `(escala, desplazamiento = 128·(1−v))` |
| E07 | Imagen persistente | `jugador_ID.png/jpg` sin rutas manipulables |
| E08 | Playlist de voz | Anterior/siguiente circular con validación de índice y dirección |
| E09 | Once 4-3-3 | 11 jugadores distintos con reparto 1/4/3/3 |
| E10 | Colecciones | Nombres únicos ignorando tildes, mayúsculas y espacios |
| E11 | Copia de seguridad | Validación completa del JSON antes de escribir; conserva los datos ausentes |
| E12 | Datos sin conexión | Distingue respuesta vacía válida de error; caché marcada como caducada |
| E13 | Reto de 5 preguntas | Preguntas sin repetir jugador, dos opciones, una correcta |
| E14 | Cromo compartible | Título 1–28 caracteres y color 0–2 |
| E15 | Intercambio Bluetooth | Mensaje ≤ 8192 bytes, versión 1, IDs enteros, únicos y conocidos |
| E16 | Panel de colección | Recuento por club sin duplicar IDs, ordenado por club |

## Requisitos

- Android Studio (reciente) con **JDK 17** y **Android SDK 35**
- Dispositivo o emulador con **API 26+**
- Versiones fijadas: AGP 8.7.3 · Kotlin 2.0.21 · Gradle 8.9 (wrapper incluido)

## ▶Cómo ejecutarlo

```bash
cd resuelto          # o cd original
./gradlew assembleDebug
adb install -r app/build/outputs/apk/debug/app-debug.apk
```

En Windows usa `gradlew.bat`.

## Cómo probarlo

```bash
# Todos los tests unitarios
./gradlew testDebugUnitTest

# Solo un ejercicio
./gradlew testDebugUnitTest --tests 'es.aula.futbol.E01Test'
```

También puedes usar la sección **Academia** dentro de la app: cada ejercicio tiene un botón *Comprobar E##* (verde = correcto, rojo = fallo con detalle, gris = `TODO` pendiente) y un botón *Comprobar los 16 ejercicios*.

- En **`original/`** los 32 tests de ejercicios fallan por `NotImplementedError`: es lo esperado.
- En **`resuelto/`** los 16 ejercicios pasan el verificador de la app (`Checker.kt`).

## Pruebas manuales (requieren móvil real)

Agitar el móvil (E05), conservar imagen tras reiniciar (E07), grabar y reproducir comentarios de voz (E08) e intercambiar colecciones entre dos equipos emparejados (E15).

## Autor

**Óscar Renilla Rodríguez** - [@OscarRenilla](https://github.com/OscarRenilla)
