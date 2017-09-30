# El script Laptop

> Visita el repositorio oficial en GitHub para que revises todo lo que configura e instala el script: https://github.com/thoughtbot/laptop

Este script se encargará de la parte más “intensa” de la instalación. Con sólo tres líneas de código y unos 15–20 minutos (para descargar e instalar automáticamente) habrá configurado prácticamente todo lo que vamos a necesitar. 

Para comenzar abre iTerm y copia/pega cada una de las siguientes líneas de código.

1. Esta línea descargará el script a tu computadora

  ```shell
  curl --remote-name https://raw.githubusercontent.com/thoughtbot/laptop/master/mac
  ```

2. Esta línea te permite revisar el script antes de ejecutarlo — **evita ejecutar scripts que no haz leído!**

  ```shell
  less mac
  ```
3. Esta línea ejecuta el script que descargaste

  ```shell
  sh mac 2>&1 | tee ~/laptop.log
  ```

  Durante los próximos 15–20 minutos tu computadora estará descargando y configurando múltiples herramientas. 

  Recuerda visitar el repositorio de [laptop](https://github.com/HoracioChavez/laptop/blob/553d3b768b19e0f1faffced266cf2565f0efac70/README-ES.md) en GitHub para que veas todos los detalles de este script antes y después de instalarlo.
