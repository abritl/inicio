# RubyGems en Windows

> Versión Alpha. Esta guía requiere probarse en distintas versiones de windows, así como documentar mejor el proceso. Si quieres apoyar las mejoras de esta guía, puedes reportar issues en GitHub, y bueno... Pull Requests son extremadamente bienvenidas :D

Para instalar RubyGems (El contenedor más popular de Gemas y que usarás muy probablemente en todos tus proyectos de con Ruby on Rails) sólo visita su página y descarga el archivo `.zip`

![rubygems download](https://s3-us-west-2.amazonaws.com/codigosemilla-bank/rubygems-download.png)

<br><br><br>
Ahora descomprime el archivo zip en una carpeta temporal.

Ahora, abre tu `Command Prompt` y navega hasta entrar a la carpeta temporal de tus RubyGems que acabas de crear. Una vez ahí, desde el prompt escribe:

```sh
ruby setup.rb
```

Al terminar, cierra tu `command prompt` y abre uno nuevo. Ahora puedes que RubyGems está instalado escribiendo el siguiente comando.

```sh
gem -v
```

Te debe regresar un número de versión. 
