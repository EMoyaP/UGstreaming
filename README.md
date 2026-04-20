# UGstreaming (Android)

Aplicacion Android de **UGstreaming** basada en WebView, construida a partir de `recomienda.html` y optimizada para uso movil.

## Estado del proyecto

- Version Android funcional y probada.
- APK generada para pruebas locales.
- Enfoque actual: cliente Android (WebView) + assets web embebidos.

## Caracteristicas

- Carga local del frontend desde `assets/web/recomienda.html`.
- Cache y almacenamiento local habilitados para mejorar rendimiento.
- Interfaz Android nativa con `Material 3`, barra superior y `pull-to-refresh`.
- Navegacion hacia atras integrada con historial del WebView.
- Splash screen y recursos de app adaptados para UGstreaming.

## Estructura

- `android-app/`: proyecto Android (Gradle).
- `recomienda.html`: fuente web original.
- `15c6f351-7108-4176-bc3a-35c9eb39992c.png`: icono base usado en la app.
- `LICENSE`: licencia de uso no comercial.

## Requisitos

- JDK 17
- Android SDK (API 35 recomendado)
- Gradle Wrapper (incluido en `android-app/`)

## Compilacion

Desde `android-app`:

```bash
./gradlew assembleDebug
./gradlew assembleRelease
```

En Windows PowerShell:

```powershell
.\gradlew.bat assembleDebug
.\gradlew.bat assembleRelease
```

## APK de debug

Salida esperada:

- `android-app/app/build/outputs/apk/debug/app-debug.apk`

Instalacion por ADB:

```bash
adb install -r android-app/app/build/outputs/apk/debug/app-debug.apk
```

## Notas de licencia

Este repositorio se distribuye para **uso no comercial**. Revisa el archivo `LICENSE` para los terminos aplicables.

## Roadmap recomendado

- Firma release con keystore de produccion.
- Separar claves/API sensibles del HTML embebido hacia configuracion segura.
- Pipeline CI para build automatica de APK.
