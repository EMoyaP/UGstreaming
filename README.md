# UGstreaming

UGstreaming es una app Android para descubrir peliculas y series disponibles en streaming en Espana.

La aplicacion combina datos de catalogo (TMDB), disponibilidad por plataforma y una capa de resumen/analisis asistida por IA para ofrecer fichas mas utiles antes de elegir que ver.

## Que hace la app

- Muestra recomendaciones de peliculas y series para Espana.
- Permite filtrar por plataforma, genero, tipo de contenido y orden.
- Consulta disponibilidad por proveedor de streaming.
- Abre detalle completo por titulo con informacion enriquecida.
- Genera resumen argumental sin spoilers mediante IA (segun proveedor habilitado).
- Muestra metadatos relevantes: reparto principal, resenas y enlaces de referencia.
- Soporta interfaz multilenguaje (espanol, ingles, frances).

## Arquitectura tecnica

El proyecto publicado corresponde a la version Android probada.

- `android-app/`: contenedor Android nativo (Kotlin + WebView).
- `android-app/app/src/main/assets/web/recomienda.html`: frontend principal con la logica funcional.
- `android-app/app/src/main/java/com/pelisyseries/app/MainActivity.kt`: configuracion WebView, navegacion, refresco y rendimiento.

### Stack

- Kotlin (Android)
- Android WebView
- Material 3
- Gradle (wrapper)
- HTML/CSS/JavaScript embebido en assets

## Rendimiento y UX en Android

- Carga local de la web desde assets para arranque rapido.
- Cache y almacenamiento local habilitados.
- Aceleracion por hardware en WebView.
- Pull-to-refresh.
- Toolbar nativa con navegacion atras.
- Splash screen e iconografia adaptada a UGstreaming.

## Requisitos

- JDK 17
- Android SDK (API 35 recomendado)
- Dispositivo Android 7.0+ (minSdk 24)

## Compilacion

Desde `android-app`:

```powershell
.\gradlew.bat assembleDebug
.\gradlew.bat assembleRelease
```

Salida principal de debug:

- `android-app/app/build/outputs/apk/debug/app-debug.apk`

Instalacion por ADB:

```powershell
adb install -r android-app/app/build/outputs/apk/debug/app-debug.apk
```

## Licencia

Uso no comercial. Consulta [LICENSE](LICENSE).

## Estado actual

- Version Android funcional y validada en pruebas locales.
- Base preparada para evolucion a version release firmada y publicable.

## Roadmap

- Firma de APK/AAB para distribucion.
- Externalizar y securizar claves/API sensibles.
- CI/CD para builds automaticas.
- Observabilidad de errores y metricas de uso.
