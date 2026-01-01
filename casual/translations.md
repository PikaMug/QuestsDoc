# 翻译

如果您希望更改插件的语言，Quests 提供了许多本地化文件，默认位于 /plugins/Quests/lang/**ISO**/strings.yml，其中“**ISO**”代表您偏好的[语言代码](https://support.crowdin.com/api/language-codes/)。翻译通过 [Crowdin](https://crowdin.com/project/translate-quests) 平台提供，任何人都可以贡献，源语言为英语（en-US）。

您可以通过修改 [config.yml](https://pikamug.gitbook.io/quests/setup/configuration#config.yml) 中的 `language` 值来选择服务器使用的语言代码。如果某个特定字符串/句子尚未本地化，它将默认显示为英语。为了避免这种情况，您可以直接编辑 strings.yml 文件，或者在 [Crowdin 上贡献翻译](https://crowdin.com/project/translate-quests)。

{% hint style="info" %}
**专业提示：** 由于众包本地化的原因，某些菜单选项可能难以使用。将配置项 `ask-confirmation` 设置为 `false` 可以帮助减少这些问题。
{% endhint %}

### 查看

在英文系统的电脑上打开包含非英文字符的 strings.yml 文件时，可能无法正确显示这些字符。在 Windows 系统下，这是因为英文版 Windows 使用 ANSI 字符集，而推荐的格式是 UTF-8。不幸的是，Windows 更改此设置较为困难，因此我们推荐使用支持 UTF-8 的编辑程序。[Notepad++](https://notepad-plus-plus.org/) 是一个受欢迎的选择。

### 更新

每次更新 Quests 时，新的语言字符串有时会添加到与您所选语言文件相同文件夹中的一个单独文件中。该文件名与当前文件相似，但结尾会附加“_new”（例如，“en-US/strings_new.yml” 或 “fr-FR/strings_new.yml”）。只需将新文件中的字符串复制到您的当前文件中即可。

如果您尚未编辑默认语言文件，也可以直接删除该文件，让 Quests 在下次服务器启动时创建一个包含更新字符串的新文件。

### 编辑

首先，请了解每个字符串由“键”（key）和“值”（value）组成。“键”帮助插件识别该字符串的用途，以下用 **粗体** 表示。“值”是引号内的部分，用户将看到的内容，通常可以翻译，以下用 _斜体_ 表示。

> **COMMAND_LIST_HELP:** "`<command>` _[page] - 列出可用任务_"

请注意 `<command>` 既没有 **粗体** 也没有 _斜体_。这是因为尽管它是值的一部分，但通常不应编辑。Quests 会用重要内容替换值的这一部分，在本例中是一个玩家命令。

为了加深理解，以下是编辑语言文件时应遵循的一些提示：

* **请** 保留每个值两端的双引号。
* **请** 随意在翻译中使用方括号 [] 和圆括号 ()。
* **请勿** 编辑键。只编辑值。
* **请勿** 在任何值中添加双引号 "，否则很可能导致错误。单引号 ' 是允许的。
* **请勿** 修改尖括号 <> 内的任何内容。您可以移动它或完全删除它，但不能翻译它。
* 无法通过语言文件更改 /quests、/quest 和 /questadmin 命令。

如果您不确定自己的编辑是否正确，或者启动时出现错误，请尝试使用在线 YAML 解析器检查您的语言文件。一个这样的解析器可以在[这里](http://yaml-online-parser.appspot.com/)找到。

### 格式化

您可以在语言文件中使用以下任意格式化标记。

| 标记            | 等价代码 | 描述                         |
| --------------- | -------- | ---------------------------- |
| %black%         | §0       | 黑色                         |
| %darkblue%      | §1       | 深蓝色                       |
| %darkgreen%     | §2       | 深绿色                       |
| %darkaqua%      | §3       | 深青色                       |
| %darkred%       | §4       | 深红色                       |
| %purple%        | §5       | 深紫色                       |
| %gold%          | §6       | 金色                         |
| %gray%          | §7       | 灰色（银色）                 |
| %darkgray%      | §8       | 深灰色                       |
| %blue%          | §9       | 蓝色                         |
| %green%         | §a       | 绿色                         |
| %aqua%          | §b       | 青色                         |
| %red%           | §c       | 红色                         |
| %pink%          | §d       | 浅紫色（粉色）               |
| %yellow%        | §e       | 黄色                         |
| %white%         | §f       | 白色                         |
| %magic%         | §k       | 随机字符格式                 |
| %bold%          | §l       | **粗体** 格式                |
| %strikethrough% | §m       | ~~删除线~~ 格式              |
| %underline%     | §n       | 下划线格式                   |
| %italic%        | §o       | _斜体_ 格式                  |
| %reset%         | §r       | 重置为默认                   |
| %br%            | N/A      | 换行字符                     |
| %tab%           | N/A      | 制表符                       |
| %rtr%           | N/A      | 回车字符                     |

在兼容版本中，支持十六进制颜色格式，例如 `%#c89664%`。

#### PlaceholderAPI

从 Quests 3.2.4 开始，[PlaceholderAPI](https://www.spigotmc.org/wiki/placeholderapi/) 的占位符（称为“[placeholders](https://www.spigotmc.org/wiki/placeholderapi-placeholders/)”）可以在玩家通常遇到的字符串中使用。管理员字符串（如任务编辑器和动作编辑器的字符串）不支持占位符。以下是如何使用玩家名称自定义字符串的示例。

之前： `journalPutAway: "You put away your Quest Journal."`

之后： `journalPutAway: "You put away %player_name%'s Quest Journal."`

请注意，“journalTitle” 字符串不支持占位符，因为允许在那里使用占位符会破坏书籍的元数据。如果您不确定某个字符串是否支持占位符，最好的做法就是直接尝试！

### 故障排除

如果您发现某些文件丢失，或者整个 /lang 文件夹缺失，请确保您的文件夹权限没有限制它们的创建。如果您使用 Windows，请右键点击 /plugins 文件夹，选择“属性”，转到“安全”选项卡。点击“高级”，然后在“权限”选项卡中选择“更改权限”。选择“添加”，在“选择用户或组”窗口中，在文本框输入“everyone”。点击“检查名称”，然后选择“确定”。如果适用，勾选所有“允许”框。继续点击“确定”直到所有窗口关闭。

或者，您可以手动创建文件夹，并从[这里](https://github.com/PikaMug/Quests/tree/main/core/src/main/resources/lang)下载所需的语言文件。