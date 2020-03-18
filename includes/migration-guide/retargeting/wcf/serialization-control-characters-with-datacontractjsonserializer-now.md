---
ms.openlocfilehash: 2c532bf3778b940f68db859420dd12826e9da388
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77465993"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a>Сериализация управляющих символов с помощью DataContractJsonSerializer теперь совместима с ECMAScript версии 6 и 8

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.6.2 и более ранних версиях объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=name> сериализовал некоторые специальные управляющие символы, например \b, \f и \t, не так, как требуют стандарты ECMAScript версии 6 и 8. Начиная с .NET Framework 4.7, сериализация таких управляющих символов совместима с ECMAScript версий 6 и 8.|
|Предложение|В приложениях, предназначенных для .NET Framework 4.7, эта функция включена по умолчанию. Если оно нежелательно, данную функцию можно отключить, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config или web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Version|4.7|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li></ul>|
