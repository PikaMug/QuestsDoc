# Translations

Should you wish to change the plugin's language, Quests has many localization files which are located at /plugins/Quests/lang/**ISO**/strings.yml by default, where "**ISO**" represents your preferred [language code](https://support.crowdin.com/api/language-codes/). Translations are provided [via Crowdin](https://crowdin.com/project/translate-quests), a platform where anyone can contribute, with English(en-US) being the source language.

You may select the language of choice for your server by changing the [language code](https://support.crowdin.com/api/language-codes/) value of `language` in [config.yml](https://pikamug.gitbook.io/quests/setup/configuration#config.yml). If a particular string/sentence has not been localized, it will default to English. To avoid this, you may edit the strings.yml file directly or [contribute a translation on Crowdin](https://crowdin.com/project/translate-quests).

{% hint style="info" %}
**Pro-tip:** Certain menu options may be difficult to use as a result of crowdsourced localization. Setting the config value of `ask-confirmation` to `false` may help minimize these issues.
{% endhint %}

### Viewing

Opening a strings.yml file that contains non-English characters on an English computer may not display those characters correctly. In the case of Windows, this is because Windows in English uses the ANSI character set, while the preferred format is UTF-8. Unfortunately, Windows makes this difficult to change, so we recommend an editing program that supports UTF-8. [Notepad++](https://notepad-plus-plus.org/) is a popular choice.

### Updates

New language strings will sometimes be added to a separate file in the same folder as your chosen language file whenever you update Quests. This file will be named similarly to your current file, but with "\_new" appended at the end of the name (for example, "en-US/strings\_new.yml" or "fr-FR/strings\_new.yml"). Simply copy the strings from this new file into your current one.

If you haven't edited the default language file, you could also simply delete the file and allow Quests to create a new one with the updated strings next time the server is started.

### Editing

First, know that each string is made of a "key" and a "value". The "key" helps the plugin know what to use the string for and is shown below in **BOLD**. The "value" is the part inside quotes that your users will see and can usually be translated. It is shown in _ITALIC_.

> **COMMAND\_LIST\_HELP:** "`<command>` _\[page] - List available Quests_"

Notice that `<command>` is neither **BOLD** nor _ITALIC_. This is because even though it's part of the value, it generally should not be edited. Quests replaces this part of the value with something important, in this case, a player command.

To solidify, here are some tips to follow when editing a language file:

* **DO** keep the double quotation marks on the ends of each value.
* **DO** feel free to use regular brackets \[] and parentheses () in your translations.
* Do **NOT** edit the key. Only edit the value.
* Do **NOT** add double quotation marks " in any of your values or you will likely break them. Single quotes ' are OK.
* Do **NOT** change anything inside angle brackets <>. You're welcome to move it around or delete it entirely, but it cannot be translated.
* It is not possible to change the /quests, /quest and /questadmin commands via the language files.

If you are ever unsure about whether your edits are correct, or you receive errors on startup, try using an online YAML parser to check your language file. One such parser can be found [here](http://yaml-online-parser.appspot.com/).

### Formatting

You may put any of the following formatting tokens into your language files.

| Token           | Equivalent | Description                  |
| --------------- | ---------- | ---------------------------- |
| %black%         | §0         | Black color                  |
| %darkblue%      | §1         | Dark blue color              |
| %darkgreen%     | §2         | Dark green color             |
| %darkaqua%      | §3         | Dark aqua color              |
| %darkred%       | §4         | Dark red color               |
| %purple%        | §5         | Dark purple color            |
| %gold%          | §6         | Gold color                   |
| %gray%          | §7         | Gray (silver) color          |
| %darkgray%      | §8         | Dark gray color              |
| %blue%          | §9         | Blue color                   |
| %green%         | §a         | Green color                  |
| %aqua%          | §b         | Aqua color                   |
| %red%           | §c         | Red color                    |
| %pink%          | §d         | Light purple (pink) color    |
| %yellow%        | §e         | Yellow color                 |
| %white%         | §f         | White color                  |
| %magic%         | §k         | Obfuscated formatting        |
| %bold%          | §l         | **Bold** formatting          |
| %strikethrough% | §m         | ~~Strikethrough~~ formatting |
| %underline%     | §n         | Underline formatting         |
| %italic%        | §o         | _Italic_ formatting          |
| %reset%         | §r         | Reset to default             |
| %br%            | N/A        | Line break character         |
| %tab%           | N/A        | Tab character                |
| %rtr%           | N/A        | Return carriage character    |

Example of hex color format is `%#c89664%` on compatible versions.

#### PlaceholderAPI

Starting with Quests 3.2.4, [PlaceholderAPI](https://www.spigotmc.org/wiki/placeholderapi/) tokens (called "[placeholders](https://www.spigotmc.org/wiki/placeholderapi-placeholders/)") can be used in strings which your players typically encounter. Admin strings, like those for the Quests and Actions editors will not accept placeholders. The following is an example of how to customize a string with a player's name.

Before: `journalPutAway: "You put away your Quest Journal."`

After: `journalPutAway: "You put away %player_name%'s Quest Journal."`

Be advised that the "journalTitle" string will not accept placeholders, as allowing tokens there would break the book's metadata. If you're skeptical as to whether a string will accept a placeholder, best practice is to just try it!

### Troubleshooting

If you find that certain files are gone, or the entire /lang folder is missing, make sure your folder permissions are not restricting their creation. If you're on Windows, right-click on your /plugins folder, select Properties, and go to the Security tab. Click "Advanced" and then, in the Permissions tab, select "Change Permissions". Choose "Add" and in the Select User or Group window, type "everyone" in the text box. Click "Check Names" and then choose "OK". If applicable, check all "Allow" boxes. Continue clicking "OK" until all windows are closed.

Alternatively, you can create the folders manually and download your desired language file(s) from [here](https://github.com/PikaMug/Quests/tree/main/core/src/main/resources/lang).
