# Comandos y Permisos

Los tres comandos principales para Quests son **/quests**, **/quest** y **/questadmin**. Los dos primeros están habilitados para todos los usuarios de forma predeterminada, mientras que el último está reservado para operaciones del servidor. Para cambiar este comportamiento, como dar **/questadmin** a administradores no operativos, debe configurar [permisos](https://bukkit.fandom.com/wiki/Understanding\_Permissions).

### Comandos del Jugador

A continuación se muestra un cuadro que describe cada comando y su permiso asociado. Tenga en cuenta que los subcomandos (listar, tomar, salir, etc.) pueden cambiar si [selecciona otro idioma del complemento](../casual/translations.md), pero los permisos seguirán siendo los mismos.

| Command                  | Permission       | Description                                 |
| ------------------------ | ---------------- | ------------------------------------------- |
| /quests                  | quests.quests    | Mostrar ayuda del complemento               |
| /quests list \[pagina]   | quests.list      | Listar misiones disponibles                 |
| /quests take \[búsqueda] | quests.take      | Aceptar una misión mediante comando         |
| /quests quit \[búsqueda] | quests.quit      | Salir de una misión actual                  |
| /quests stats            | quests.stats     | Ver estadísticas de misiones                |
| /quests top \[número]    | quests.top       | Ver tablas de clasificación de complementos |
| /quests info             | quests.info      | Ver información del complemento             |
| /quests journal          | quests.journal   | Alternar el Diario de Misiones              |
| N/A                      | quests.compass   | Seguimiento de misiones usando una Brújula  |
| N/A                      | quests.choice    | Utilice texto en el que se pueda hacer clic |
|                          |                  |                                             |
| /quest                   | quests.quest     | Ver objetivos de misión actuales            |
| /quest \[búsqueda]       | quests.questinfo | Ver información sobre una misión            |

{% hint style="info" %}
Co**nsejo-pro:** De forma predeterminada, también puedes usar **/qs** y **/q** en lugar de **/quests** y **/quest**, respectivamente.
{% endhint %}

### Comandos de Administrador

Los comandos de administrador, que sólo deben concederse a aquellas personas en las que usted confía para que no los utilicen indebidamente, se describen a continuación.

| Command                                                | Permission               | Description                                           |
| ------------------------------------------------------ | ------------------------ | ----------------------------------------------------- |
| /questadmin                                            | quests.admin             | Mostrar ayuda del administrador                       |
| /questadmin stats \[jugador]                           | quests.admin.stats       | Ver estadísticas de búsqueda de un jugador            |
| /questadmin give \[jugador] \[misión]                  | quests.admin.give        | Obliga a un jugador a tomar una misión                |
| /questadmin quit \[jugador] \[misión]                  | quests.admin.quit        | Forzar a un jugador a salir de una búsqueda           |
| /questadmin points \[jugador] \[cantidad]              | quests.admin.points      | Establecer los Puntos de Misión de un jugador         |
| /questadmin takepoints \[jugador] \[cantidad]          | quests.admin.takepoints  | Quitar los Puntos de Misión de un jugador             |
| /questadmin givepoints \[jugador] \[cantidad]          | quests.admin.givepoints  | Añadir a los Puntos de Misión de un jugador           |
| /questadmin finish \[jugador] \[misión]                | quests.admin.finish      | Obligar a un jugador a completar una misión           |
| /questadmin nextstage \[jugador] \[misión]             | quests.admin.nextstage   | Obliga a un jugador a completar la etapa actual       |
| /questadmin setstage \[jugador] \[misión] \[escenario] | quests.admin.setstage    | Establecer el escenario actual para un jugador        |
| /questadmin reset \[jugador]                           | quests.admin.reset       | Borrar todos los datos de Quests de un jugador        |
| /questadmin remove \[jugador] \[misión]                | quests.admin.remove      | Eliminar una misión completada de un jugador          |
| /questadmin reload                                     | quests.admin.reload      | Recarga el complemento de forma segura                |
| N/A                                                    | quests.admin.drop        | Posibilidad de soltar el Diario de Misiones           |
| N/A                                                    | quests.admin.update      | Ver avisos de actualización del complemento           |
| N/A                                                    | quests.mode.trial        | Acceso limitado a editores, deshabilitado por defecto |
| /quests editor                                         | quests.editor.editor     | Posibilidad de abrir el Editor de Misiones            |
| N/A                                                    | quests.editor.create     | Capacidad para crear nuevas misiones                  |
| N/A                                                    | quests.editor.edit       | Posibilidad de editar misiones existentes             |
| N/A                                                    | quests.editor.delete     | Posibilidad de eliminar misiones existentes           |
| /quests actions                                        | quests.actions.editor    | Capacidad para abrir el Editor de Acciones            |
| N/A                                                    | quests.actions.create    | Capacidad para crear nuevas acciones                  |
| N/A                                                    | quests.actions.edit      | Posibilidad de editar acciones existentes             |
| N/A                                                    | quests.actions.delete    | Posibilidad de eliminar acciones existentes           |
| /quests conditions                                     | quests.conditions.editor | Capacidad para abrir el Editor de Condiciones         |
| N/A                                                    | quests.conditions.create | Capacidad de crear nuevas condiciones                 |
| N/A                                                    | quests.conditions.edit   | Capacidad para editar condiciones existentes          |
| N/A                                                    | quests.conditions.delete | Posibilidad de eliminar condiciones existentes        |

{% hint style="info" %}
Co**nsejo-pro:** Utilice _quests.admin.\*_, _quests.editor.\*_, _quests.actions.\*_ y _quests.conditions.\*_ para abarcar todos los permisos de administrador y editor, respectivamente. ¡De forma predeterminada, también puedes usar **/qa** en lugar de **/questadmin**!
{% endhint %}
