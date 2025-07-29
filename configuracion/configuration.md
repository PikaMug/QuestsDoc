# Configuración

Cuando Quests se ejecuta por primera vez, los archivos de configuración se crearán en el directorio /plugins/Quests. Si es la primera vez que usa Quests, asegúrese de que la configuración en **config.yml** sea de su agrado. No se preocupe por ninguno de los otros archivos o carpetas por el momento.

{% hint style="info" %}
**Pro-consejo:** Abrir un archivo .yml que contiene caracteres que no están en inglés en una computadora en inglés puede no mostrar esos caracteres correctamente. En el caso de Windows, esto se debe a que Windows en inglés utiliza el juego de caracteres ANSI, mientras que el formato preferido es UTF-8. Desafortunadamente, Windows hace que esto sea difícil de cambiar, por lo que recomendamos un programa de edición que admita UTF-8. [Notepad++](https://notepad-plus-plus.org/) es una opción gratuita y popular.
{% endhint %}

### config.yml

Este archivo contiene todas las configuraciones relacionadas con el rendimiento de las misiones una vez cargadas. Como tal, los cambios realizados en este archivo deben configurarse y guardarse _antes_ de iniciar el servidor.

> [Haga clic aquí para ver el archivo config.yml predeterminado.](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/config.yml)

| Key                                           | Data Type       | Description                                                                                                                                                               |
| --------------------------------------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| accept-timeout                                | número          | Cuánto tiempo (en segundos) un jugador debería poder aceptar/rechazar una misión antes de que el mensaje se cancele automáticamente.                                      |
| allow-command-questing                        | verdadero/falso | Si los jugadores pueden aceptar y administrar misiones mediante comandos (por ejemplo, /quests toman AlgunaQuest).                                                        |
| allow-command-quests-with-npcs                | verdadero/falso | Si los jugadores pueden aceptar/administrar misiones de NPC mediante comandos (por ejemplo, /quests toman AlgunaQuest).                                                   |
| allow-pranks                                  | verdadero/falso | Si se permite hacer clic en Portales con el Diario de Misiones.                                                                                                           |
| clickable-prompts                             | verdadero/falso | Haga clic en la mayoría de las selecciones rápidas en el chat.                                                                                                            |
| condition-interval                            | número          | Cuánto tiempo (en segundos) transcurre entre notificaciones de condición (mínimo 3, máximo 180).                                                                          |
| confirm-accept                                | verdadero/falso | Si los jugadores deben confirmar la toma de una misión.                                                                                                                   |
| confirm-abandon                               | verdadero/falso | Si los jugadores deben confirmar el abandono de una misión.                                                                                                               |
| console-logging                               | número          | 0 = deshabilitado, 1 = edición de seguimiento, 2 = e iniciar/salir de misiones, 3 = y recompensas, 4 = e información de depuración.                                       |
| disable-command-feedback                      | verdadero/falso | Si se debe deshabilitar la regla de juego sendCommandFeedback de Minecraft al inicio.                                                                                     |
| generate-files-on-join                        | verdadero/falso | Genere un archivo de datos del jugador cuando ese jugador se una por primera vez al servidor o solo cuando use Quests por primera vez.                                    |
| give-journal-item                             | verdadero/falso | Quest Journal existe como elemento en el inventario del jugador.                                                                                                          |
| ignore-locked-quests                          | verdadero/falso | Ignora las misiones bloqueadas cuando compruebes si un jugador tiene todos los requisitos necesarios.                                                                     |
| kill-delay                                    | número          | Cuánto tiempo (en segundos) debe esperar un jugador después de matar a un jugador para una misión antes de poder matarlo nuevamente.                                      |
| language                                      | texto           | Qué archivo de la carpeta /lang/ se utilizará para el texto administrativo. Por ejemplo, un valor de "FR-fr" dará como resultado que se cargue "/lang/FR-fr/strings.yml". |
| language-override-client                      | verdadero/falso | Si la configuración de `language` debe anular el idioma del cliente al enviar texto.                                                                                      |
| max-quests                                    | número          | Número máximo de misiones que un jugador determinado puede tener en cualquier momento.                                                                                    |
| npc-effects.enabled                           | verdadero/falso | Ya sea para habilitar los efectos de partículas. Tenga en cuenta que el cliente debe tener las partículas habilitadas.                                                    |
| npc-effects.new-quest                         | texto           | El efecto de partículas que se reproducirá en una nueva misión (por ejemplo, nota, encantamiento, crítico, hechizo, portal).                                              |
| npc-effects.redo-quest                        | texto           | El efecto de partículas que se reproducirá en una misión repetible (por ejemplo, nota, encantamiento, crítico, hechizo, portal).                                          |
| prevent-exploit                               | verdadero/falso | Intente evitar vulnerabilidades de inventario en las misiones correspondientes.                                                                                           |
| show-requirements                             | verdadero/falso | Permitir a los jugadores ver requisitos en / quest \[quest]                                                                                                               |
| show-titles                                   | verdadero/falso | Mostrar títulos a los jugadores al aceptar / completar misiones.                                                                                                          |
| strict-player-movement                        | número          | Segundos entre seguimiento avanzado del movimiento del jugador.                                                                                                           |
| storage-data.address                          | texto           | La dirección IP para el almacenamiento opcional.                                                                                                                          |
| storage-data.database                         | texto           | El nombre de la tabla para el almacenamiento opcional.                                                                                                                    |
| storage-data.username                         | texto           | El nombre de usuario de inicio de sesión para almacenamiento opcional.                                                                                                    |
| storage-data.password                         | texto           | La contraseña de inicio de sesión para almacenamiento opcional.                                                                                                           |
| storage-data.pool-settings.max-pool-size      | número          | Configuración avanzada de HikariCP.                                                                                                                                       |
| storage-data.pool-settings.min-idle           | número          | Configuración avanzada de HikariCP.                                                                                                                                       |
| storage-data.pool-settings.max-lifetime       | número          | Advanced HikariCP setting.                                                                                                                                                |
| storage-data.pool-settings.connection-timeout | número          | Advanced HikariCP setting.                                                                                                                                                |
| storage-method.player-data                    | texto           | yaml = file storage, mysql = remote storage, custom = developer storage                                                                                                   |
| top-limit                                     | número          | Maximum number of quests that can be displayed by /quests top \[number]                                                                                                   |
| translate-names                               | verdadero/falso | Translate item/mob name to client's game language.                                                                                                                        |
| translate-subcommands                         | verdadero/falso | Translate subcommands to server's plugin language.                                                                                                                        |
| trial-save                                    | verdadero/falso | Allow saving while in Trial Mode.                                                                                                                                         |
| update-check                                  | verdadero/falso | Whether to permit checking for plugin updates.                                                                                                                            |

### actions.yml

{% hint style="info" %}
Manually editing this file is not advised. No support will be given to those whom choose not to use the in-game editor.
{% endhint %}

This file holds actions which execute certain tasks and effects. Except for the included examples, actions are created prior to use in a quest. This is best accomplished with the _/quests actions_ command.

> [Click here to view the default actions.yml file.](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/actions.yml)

### conditions.yml

{% hint style="info" %}
Manually editing this file is not advised. No support will be given to those whom choose not to use the in-game editor.
{% endhint %}

This file holds conditions which are checked during gameplay. Except for the included examples, conditions are created prior to use in a quest. This is best accomplished with the _/quests conditions_ command.

> [Click here to view the default conditions.yml file.](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/conditions.yml)

### quests.yml

{% hint style="info" %}
Manually editing this file is not advised. No support will be given to those whom choose not to use the in-game editor.
{% endhint %}

This file contains all saved quests. A few example quests are included which you may delete at any time. This is best accomplished with the _/quests editor_ command.

> [Click here to view the default quests.yml file.](https://github.com/PikaMug/Quests/blob/main/core/src/main/resources/quests.yml)
