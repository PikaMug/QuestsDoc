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

| Command                                          | Permission               | Description                                    |
| ------------------------------------------------ | ------------------------ | ---------------------------------------------- |
| /questadmin                                      | quests.admin             | Mostrar ayuda del administrador                |
| /questadmin stats \[player]                      | quests.admin.stats       | Ver estadísticas de búsqueda de un jugador     |
| /questadmin give \[player] \[quest]              | quests.admin.give        | Obliga a un jugador a tomar una misión         |
| /questadmin quit \[player] \[quest]              | quests.admin.quit        | Forzar a un jugador a salir de una búsqueda    |
| /questadmin points \[player] \[amount]           | quests.admin.points      | Establecer los Puntos de Misión de un jugador  |
| /questadmin takepoints \[player] \[amount]       | quests.admin.takepoints  | Quitar los Puntos de Misión de un jugador      |
| /questadmin givepoints \[player] \[amount]       | quests.admin.givepoints  | Add to a player's Quest Points                 |
| /questadmin finish \[player] \[quest]            | quests.admin.finish      | Force a player to complete a quest             |
| /questadmin nextstage \[player] \[quest]         | quests.admin.nextstage   | Force a player to complete current stage       |
| /questadmin setstage \[player] \[quest] \[stage] | quests.admin.setstage    | Set the current stage for a player             |
| /questadmin reset \[player]                      | quests.admin.reset       | Clear all Quests data of a player              |
| /questadmin remove \[player] \[quest]            | quests.admin.remove      | Remove a completed quest from a player         |
| /questadmin reload                               | quests.admin.reload      | Safely reload the plugin                       |
| N/A                                              | quests.admin.drop        | Ability to drop the Quests Journal             |
| N/A                                              | quests.admin.update      | View plugin update notices                     |
| N/A                                              | quests.mode.trial        | Limited access to editors, disabled by default |
| /quests editor                                   | quests.editor.editor     | Ability to open Quests Editor                  |
| N/A                                              | quests.editor.create     | Ability to create new quests                   |
| N/A                                              | quests.editor.edit       | Ability to edit existing quests                |
| N/A                                              | quests.editor.delete     | Ability to delete existing quests              |
| /quests actions                                  | quests.actions.editor    | Ability to open Action Editor                  |
| N/A                                              | quests.actions.create    | Ability to create new actions                  |
| N/A                                              | quests.actions.edit      | Ability to edit existing actions               |
| N/A                                              | quests.actions.delete    | Ability to delete existing actions             |
| /quests conditions                               | quests.conditions.editor | Ability to open Condition Editor               |
| N/A                                              | quests.conditions.create | Ability to create new conditions               |
| N/A                                              | quests.conditions.edit   | Ability to edit existing conditions            |
| N/A                                              | quests.conditions.delete | Ability to delete existing conditions          |

{% hint style="info" %}
**Pro-tip:** Use _quests.admin.\*_, _quests.editor.\*_, _quests.actions.\*_ and _quests.conditions.\*_ to encompass all admin and editor permissions, respectively! By default, you can also use **/qa** instead of **/questadmin**!
{% endhint %}
