# Ruby en Windows

> Versión Alpha. Esta guía requiere probarse en distintas versiones de windows, así como documentar mejor el proceso. Si quieres apoyar las mejoras de esta guía, puedes reportar issues en GitHub, y bueno... Pull Requests son extremadamente bienvenidas :D

Lo primero que haremos para instalar Ruby será visitar: https://rubyinstaller.org y dar click en el botón "Download".

![ruby installer](https://s3-us-west-2.amazonaws.com/codigosemilla-bank/rubyinstaller.png)

<br><br><br>

Ahora, vamos a descargar un `.zip` con la versión de Ruby que necesitamos. Es recomendable que descargues la versión más reciente, sin embargo si estás manteniendo un app con alguna versión antigua, también puedes descargarla.

![ruby installer](https://s3-us-west-2.amazonaws.com/codigosemilla-bank/rubyinstaller-versions.png)

<br><br><br>

**Antes de descargar Ruby**, necesitas saber que versión necesitas (`x64` o `x86`). Para esto aprieta las teclas `Windows` y `R` a la vez. En el campo escribe `dxdiag` y haz click en `ok`. Ahora ya puedes identificar tu sitema operativo.

![ruby installer](https://s3-us-west-2.amazonaws.com/codigosemilla-bank/win-64.jpg)

<br><br><br>

Ahora, ya que sabes tu versión de Windows, ya puedes descargar la versión de Ruby que te corresponde. En caso de que lo necesites, puedes descargar [7zip](http://www.7-zip.org) para descomprimir los archivos `.zip`.

Una vez que hayas descargado el archivo `.zip`, debes descomprimirlo y copiarlo a una ubicación permanente. Asegúrate de que el nombre de la carpeta no tenga ningún espacio.

Una opción para la ubicación definitiva puede ser:

```
c:\dev\dependencias\ruby
```

<br><br><br>
Excelente! Ya tienes Ruby, ahora vamos a agregarlo a `Windows PATH`. Esto te permitirá llamar `ruby` desde tu `Command Prompt` o `Símbolo del Sistema`.

Para agregarlo ve a tu `Panel de Control` y desde la sección `Sistema` da click en el link: `Configuración Avanzada del Sistema`.

Ahora da click en el botón "Variables de Entorno" o "Environment Variables". La forma exacta de llegar a este botón varía dependiendo de tu versión de Windows.

Una vez ahí, en el área de "Variables del Sistema" busca la variable "Path", selecciónala y da click en "Editar..."

Ahora da click en "Nuevo" para agregar el directorio `bin` que está dentro del directorio que acabas de crear con la descarga de Ruby.

Podría ser algo así:

```
c:\dev\dependencias\ruby\rubyinstaller-2.4.2-2-x64\bin
```

Ahora da click en `Ok` o `Guardar` y cierra todas las instancias del `Command Prompt` o `Símbolo del Sistema` que tengas abiertas.

<br><br><br>

Ahora vamos a instalar las "build tools" que vamos a necesitar para compilar las gemas que dependen de librerías externas.

Para esto visita http://www.msys2.org y descarga la versión que corresponda a tu versión de Windows. Una vez descargado haz doble click para ejecutar el instalador.

Una vez que haya terminado vas a necesitar configurar `pacman`. Para hacer esto abre la recién instalada consola `MSYS2 MinGW 64-bit`. Una vez abierta la consola, escribe lo siguiente:

```
pacman -Sy pacman
```

Con esto `pacman` deberá estar completamente instalado. ;)

Ahora vamos instalar algunas dependencias.

Abre tu `Command Prompt` y escribe `ridk install`. Verás tres opciones, selecciona la tercera (MSYS2 and MINGW development toolchain) escribiendo el número `3` y dando `Enter`. Esto debería ser suficiente, sin embargo si esto falla deberás regresar a la consola de `MSYS` y correr uno de los siguientes comandos, dependiendo de tu versión.

```
pacman -S base-devel mingw-w64-i686-toolchain #32-bit
pacman -S base-devel mingw-w64-x86_64-toolchain #64-bit
```

Si esto tampoco funciona, debes cambiar el tamaño de la ventana de MSYS continuamente, esto ha sido reportado como necesario por algunos usuarios.

<br><br><br>


Ahora vamos a instalar las gemas Nokogiri y SQLite3 ([Aquí](https://github.com/oneclick/rubyinstaller2#install-gems-with-c-extensions-and-additional-library-dependencies) puedes encontrar más información en Inglés).

Para instlar la gema `sqlite3`:

```
ridk exec pacman -S mingw-w64-x86_64-sqlite3
gem install sqlite3 --platform ruby
```

Para instlar la gema `nokogiri`:
```
ridk exec pacman -S mingw-w64-x86_64-libxslt
gem install nokogiri --platform ruby -- --use-system-libraries
```

<br><br><br>

Y listo! Ahora si, ya deberás tener Ruby listo : )
