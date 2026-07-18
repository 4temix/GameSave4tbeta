# GameSave4t (Beta)

## ¡Hola!

Antes que nada, gracias por darle una oportunidad a **GameSave4t**.

Este proyecto nació como una iniciativa personal mientras me encontraba buscando trabajo. Quería seguir aprendiendo, mantenerme activo como desarrollador y crear una herramienta que realmente pudiera ser útil para otros jugadores.

Después de unas 3 semanas de desarrollo decidí compartirla con la comunidad. Actualmente **GameSave4t se encuentra en fase Beta**, por lo que es posible que encuentres errores o funciones que aún estén en desarrollo. Si eso ocurre, agradeceré mucho cualquier comentario o reporte para seguir mejorándola.

---

# ¿Qué es GameSave4t?

GameSave4t es una aplicación para Windows diseñada para crear copias de seguridad de las partidas guardadas (Save Data) de tus juegos.

Su objetivo es proteger tu progreso frente a situaciones como:

- Formatear el equipo.
- Cambiar de computadora.
- Daños en el disco duro.
- Eliminación accidental de archivos.
- Sincronizar tus partidas entre diferentes equipos mediante Google Drive.

Una vez registras la carpeta donde un juego guarda sus partidas, GameSave4t monitorea automáticamente esa ubicación y crea respaldos cuando detecta cambios.

---

# Inicio de sesión con Google

GameSave4t permite iniciar sesión con una cuenta de Google para sincronizar los respaldos mediante Google Drive.

Quiero dejar algo muy claro:

**Yo no tengo acceso a tu cuenta de Google ni a tus archivos.**

Todo el proceso de autenticación ocurre directamente entre la aplicación y los servicios oficiales de Google mediante OAuth.

La aplicación únicamente solicita los permisos necesarios para trabajar con la carpeta que utiliza para almacenar los respaldos.

No puedo:

- Ver tus archivos personales.
- Leer tus correos electrónicos.
- Acceder a tus fotografías.
- Obtener información privada de tu cuenta.

Toda la información permanece bajo tu propia cuenta de Google.

---

# Carpeta creada en Google Drive

Durante el primer inicio de sesión, la aplicación crea automáticamente una carpeta llamada:

**GameSave4t**

Dentro de ella se almacenarán todos los respaldos y la información necesaria para sincronizar tus juegos.

La estructura será similar a esta:

```text
Google Drive
└── GameSave4t
    ├── Juego 1
    ├── Juego 2
    ├── Juego 3
    └── ...
```

Cada juego tendrá su propia carpeta con sus respaldos y archivos de sincronización.

> **Importante**
>
> No elimines ni modifiques la carpeta **GameSave4t** ni su contenido desde Google Drive si deseas seguir utilizando la sincronización con la aplicación.
>
> Si la carpeta es eliminada, los respaldos almacenados en la nube también desaparecerán y la sincronización dejará de funcionar correctamente hasta volver a crear la estructura.

---

# ¿Cómo funciona la aplicación?

Actualmente los juegos deben registrarse manualmente.

Esto significa que debes indicarle a GameSave4t dónde guarda sus partidas cada juego que deseas respaldar.

En futuras versiones planeo incorporar una base de datos con rutas conocidas para que este proceso sea mucho más sencillo.

Una vez agregada la carpeta del juego, la aplicación comenzará a monitorearla automáticamente y generará respaldos cuando detecte cambios en los archivos.

---

# Formas de registrar la carpeta del juego

Puedes hacerlo de dos maneras.

## 1. Seleccionando la carpeta

Es la opción recomendada.

Simplemente utiliza el explorador de archivos integrado en la aplicación para seleccionar la carpeta donde el juego guarda sus partidas.

---

## 2. Escribiendo la ruta manualmente

También puedes escribir la ruta utilizando variables de entorno de Windows.

Por ejemplo:

```text
%USERPROFILE%\Documents\My Games\Skyrim\Saves

%APPDATA%\NombreDelJuego

%LOCALAPPDATA%\NombreDelJuego

%ProgramData%\NombreDelJuego
```

Esto resulta especialmente útil porque las rutas funcionan incluso cuando el nombre del usuario de Windows cambia entre diferentes equipos.

Actualmente GameSave4t reconoce las siguientes variables de entorno:

| Variable                    | Descripción                                   |
| --------------------------- | --------------------------------------------- |
| `%APPDATA%`                 | Carpeta AppData\Roaming del usuario.          |
| `%LOCALAPPDATA%`            | Carpeta AppData\Local del usuario.            |
| `%PROGRAMDATA%`             | Datos compartidos por todas las aplicaciones. |
| `%DESKTOP%`                 | Escritorio del usuario.                       |
| `%USERDOCUMENTS%`           | Documentos del usuario.                       |
| `%USERMUSIC%`               | Música del usuario.                           |
| `%USERPICTURES%`            | Imágenes del usuario.                         |
| `%USERVIDEOS%`              | Videos del usuario.                           |
| `%FAVORITES%`               | Favoritos del usuario.                        |
| `%STARTMENU%`               | Menú Inicio.                                  |
| `%STARTUP%`                 | Inicio automático de Windows.                 |
| `%SENDTO%`                  | Carpeta "Enviar a".                           |
| `%TEMPLATES%`               | Plantillas del usuario.                       |
| `%FONTS%`                   | Fuentes instaladas.                           |
| `%PROGRAMFILES%`            | Archivos de programa (64 bits).               |
| `%PROGRAMFILES(X86)%`       | Archivos de programa (32 bits).               |
| `%WINDIR%`                  | Carpeta de Windows.                           |
| `%SYSTEMROOT%`              | Carpeta del sistema operativo.                |
| `%PUBLICDOCUMENTS%`         | Documentos públicos.                          |
| `%PUBLICPICTURES%`          | Imágenes públicas.                            |
| `%PUBLICMUSIC%`             | Música pública.                               |
| `%PUBLICVIDEOS%`            | Videos públicos.                              |
| `%PUBLICDESKTOP%`           | Escritorio público.                           |
| `%USERPROFILE%`             | Carpeta principal del usuario.                |
| `%SystemDrive%`             | Unidad donde está instalado Windows.          |
| `%SystemRoot%`              | Directorio principal de Windows.              |
| `%ProgramData%`             | Datos de programas.                           |
| `%CommonProgramFiles%`      | Archivos comunes de programas.                |
| `%CommonProgramFiles(x86)%` | Archivos comunes de programas (32 bits).      |
| `%ProgramW6432%`            | Archivos de programa de 64 bits.              |
| `%ProgramFiles%`            | Archivos de programa.                         |
| `%ProgramFiles(x86)%`       | Archivos de programa (32 bits).               |
| `%PUBLIC%`                  | Carpeta pública de usuarios.                  |
| `%TEMP%`                    | Archivos temporales.                          |
| `%TMP%`                     | Carpeta temporal.                             |
| `%OneDrive%`                | Carpeta principal de OneDrive.                |
| `%OneDriveConsumer%`        | OneDrive personal.                            |
| `%OneDriveCommercial%`      | OneDrive empresarial.                         |
| `%HOMEDRIVE%`               | Unidad del perfil del usuario.                |
| `%HOMEPATH%`                | Ruta del perfil del usuario.                  |
| `%ALLUSERSPROFILE%`         | Perfil compartido por todos los usuarios.     |
| `%CommonProgramW6432%`      | Archivos comunes de programas de 64 bits.     |
| `%DriverData%`              | Datos utilizados por controladores.           |
| `%ADMINTOOLS%`              | Herramientas administrativas.                 |
| `%CDBURNING%`               | Carpeta de grabación de CD.                   |
| `%COMMONADMINTOOLS%`        | Herramientas administrativas compartidas.     |
| `%COMMONSTARTMENU%`         | Menú Inicio compartido.                       |
| `%COMMONPROGRAMS%`          | Programas compartidos.                        |
| `%COMMONSTARTUP%`           | Inicio automático compartido.                 |
| `%COMMONTEMPLATES%`         | Plantillas compartidas.                       |
| `%COOKIES%`                 | Cookies del usuario.                          |
| `%HISTORY%`                 | Historial del usuario.                        |
| `%INTERNETCACHE%`           | Caché de Internet.                            |
| `%PRINTERSHORTCUTS%`        | Accesos directos de impresoras.               |
| `%PROGRAMS%`                | Programas del usuario.                        |
| `%RECENT%`                  | Elementos recientes.                          |
| `%RESOURCES%`               | Recursos de Windows.                          |
| `%LOCALIZEDRESOURCES%`      | Recursos localizados.                         |
| `%SYSTEMX86%`               | Carpeta System32 para componentes de 32 bits. |

---

# Respaldos automáticos

Una vez que un juego ha sido registrado, GameSave4t puede crear respaldos automáticamente cada vez que detecta cambios en los archivos de guardado.

La aplicación monitorea la carpeta del juego en segundo plano y, cuando identifica que la partida ha cambiado, genera un nuevo respaldo comprimido.

No es necesario crear los respaldos manualmente después de cada sesión de juego.

---

# Sincronización automática local

Cada juego puede activar o desactivar de forma independiente la creación automática de respaldos locales.

- **Activada:** GameSave4t creará nuevos respaldos automáticamente cuando detecte cambios.
- **Desactivada:** No se crearán nuevos respaldos automáticamente para ese juego. Aun así, podrás seguir administrándolo desde la aplicación.

Esto permite decidir qué juegos deseas respaldar continuamente y cuáles prefieres gestionar manualmente.

---

# Sincronización automática con Google Drive

También es posible activar o desactivar la sincronización con Google Drive para cada juego de manera independiente.

- **Activada:** Después de crear un nuevo respaldo local, GameSave4t lo sincronizará automáticamente con tu Google Drive.
- **Desactivada:** Los respaldos permanecerán únicamente en tu equipo y no se subirán a la nube.

Esto resulta útil si deseas sincronizar solo algunos juegos y mantener otros únicamente como respaldo local.

---

# Administración de respaldos

## Respaldos locales

Para evitar que el almacenamiento crezca sin control, GameSave4t conserva únicamente los **3 respaldos más recientes** de cada juego.

Cuando se crea un cuarto respaldo, el más antiguo se elimina automáticamente.

Esto permite mantener un pequeño historial de versiones sin ocupar una cantidad excesiva de espacio en el disco.

---

## Respaldos en Google Drive

En Google Drive la aplicación mantiene únicamente **el respaldo más reciente** de cada juego.

Cada vez que se sincroniza una nueva versión, esta reemplaza a la anterior.

De esta forma:

- Se reduce el espacio utilizado en Google Drive.
- La sincronización es más rápida.
- Siempre tendrás disponible la versión más reciente de tu partida.

---

# Restaurar una partida

Si necesitas recuperar una partida anterior, puedes restaurarla desde un respaldo existente.

Actualmente es posible restaurar:

- Un respaldo almacenado localmente.
- El respaldo disponible en Google Drive.

Antes de restaurar una partida, se recomienda realizar una copia de seguridad de la carpeta actual del juego, ya que el proceso reemplazará los archivos existentes.

---

# Información que muestra cada juego

Cada juego registrado muestra información útil para conocer su estado de un vistazo.

Entre ella se encuentra:

- Nombre del juego.
- Imagen personalizada.
- Ruta donde se encuentran los archivos de guardado.
- Fecha del último respaldo.
- Estado de la sincronización local.
- Estado de la sincronización con Google Drive.
- Indicadores cuando existe una sincronización en progreso.
- Indicadores cuando existen cambios pendientes por sincronizar.

Esto permite identificar rápidamente qué juegos están protegidos, cuáles necesitan sincronizarse y si alguna operación aún está en curso.

---

# Algunas recomendaciones

Para obtener el mejor funcionamiento de la aplicación, se recomienda:

- No modificar manualmente la carpeta **GameSave4t** creada en Google Drive.
- No mover ni renombrar la carpeta de guardado de un juego después de registrarla en la aplicación. Si cambias su ubicación, actualiza la ruta desde GameSave4t.
- Mantener suficiente espacio libre tanto en el disco como en Google Drive para permitir la creación de nuevos respaldos.
- Esperar a que finalicen las sincronizaciones antes de cerrar la aplicación cuando exista una operación en progreso.

---

# Estado actual del proyecto

GameSave4t continúa en desarrollo y seguiré agregando nuevas funciones en futuras versiones.

Entre las mejoras previstas se encuentran:

- Detección automática de carpetas de guardado de juegos compatibles.
- Base de datos integrada con rutas conocidas para cientos de juegos.
- Más opciones de sincronización.
- Mejoras en la interfaz de usuario.
- Optimizaciones de rendimiento y estabilidad.

El objetivo es que, con el tiempo, la aplicación requiera la menor configuración posible y sea capaz de proteger automáticamente las partidas de la mayoría de los juegos desde el primer momento.
