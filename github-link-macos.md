# Enlaza tu mac con GitHub

Ahora que tienes tu cuenta en GitHub, ha llegado el momento de ligarla con tu mac! Para esto vamos a seguir el proceso que GitHub recomienda para autenticar via SSH. Al así, no tendrás que proporcionar tu username y contraseña cada vez que te quieras conectar – que en la práctica sucederá varias veces al día!

1. Genera una nueva llave.

  + Abre iTerm2

  + Copia la siguiente línea de código. Asegúrate de cambiar el email por el email con el que te registraste en GitHub.

  ```sh
  ssh-keygen -t rsa -b 4096 -C "tu_email@example.com"
  ```

  + Esto va a crear una nueva llave SSH.

  + Cuando veas “Enter a file in which to save the key” aprieta enter . Esto acepta la ubicación predeterminada.

  ```sh
  Enter a file in which to save the key (/Users/tu/.ssh/id_rsa): [Press enter]
  ```

  + Cuando veas “Enter passphrase (empty for no passphrase):” ingresa una frase que será tu contraseña, piensa en esto como una contraseña más larga. 

  + Te pedirá que la ingreses dos veces para confirmar que no te equivocaste al ingresarla.

  ```sh
  Enter passphrase (empty for no passphrase): [Type a passphrase]
  Enter same passphrase again: [Type passphrase again]
  ```

  Ahora agregaremos tu llave SSH al `ssh-agent`.

  + Inicia el ssh-agent asi:

  `eval "$(ssh-agent -s)"`

  + En respuesta verás algo parecido a esto:

  ```sh
  Agent pid 59566
  ```

  > En caso de que estés usando macOS Sierra 12.2 o posterior, vas a necesitar modificar tu archivo ``~/.ssh/config` para que se vea así:

  ```sh
  Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
  ```

  + Ahora agrega tu llave privada SSH al `ssh-agent`:

  ```sh
  ssh-add -K ~/.ssh/id_rsa
  ```

  Ahora vamos a agregar tu llave SSH a tu cuenta de GitHub.

  + Copia la llave SSH a tu clipboard

  ```sh
  pbcopy < ~/.ssh/id_rsa.pub
  ```

  + Abre tus ‘settings’ en GitHub dando click en tu imagen de perfil y seleccionando `settings` en el menú. También puedes dar click [aquí](https://github.com/settings/profile).

  ![github settings link](https://s3-us-west-2.amazonaws.com/codigosemilla-bank/github-settings-link.png)

  Ahora selcciona “[SSH and GPG Keys](https://github.com/settings/keys)”.

  ![github settings keys](https://s3-us-west-2.amazonaws.com/codigosemilla-bank/github-settings-keys.png)

  En la siguiente vista, selecciona: “New SSH Key”

  ![github-ssh-key](https://s3-us-west-2.amazonaws.com/codigosemilla-bank/github-ssh-key.png)

  Ahora deberás ingresar:

  + **title**: Algo que identifique la mac que estás configurando, por ejemplo: “imac_oficina”

  + **key**: pega aquí el contenido de tu llave SSH

  + Finalmente haz click en: ‘Add SSH key’.

  + Si te lo pide, ingresa tu password de GitHub

  ![github-ssh-key](https://s3-us-west-2.amazonaws.com/codigosemilla-bank/github-add-ssh.png)  

  #### Listo! Ahora ya tienes tu mac ligada con tu cuenta de GitHub!

  
