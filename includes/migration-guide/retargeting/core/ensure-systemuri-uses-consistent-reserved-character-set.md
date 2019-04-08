---
ms.openlocfilehash: 4f92d773197c914a74dd7e9c18f5aab5309358ae
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760892"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Гарантия использования System.Uri согласованного набора зарезервированных символов

|   |   |
|---|---|
|Подробные сведения|В <xref:System.Uri?displayProperty=fullName> некоторые символы, закодированные процентами, которые иногда декодировались, теперь всегда остаются закодированными. Это справедливо для свойств и методов, которые получают доступ к компонентам пути, запроса, фрагмента или сведений пользователя URI. Это поведение изменится, только если выполняются оба указанные ниже условия:<ul><li>URI содержит кодированную форму любого из следующих зарезервированных символов: <code>:</code>, <code>'</code>, <code>(</code>, <code>)</code>, <code>!</code> или <code>*</code>.</li><li>URI содержит строку в кодировке Юникоде или закодированные незарезервированные символы. Если выполняются оба приведенных выше условия, закодированные зарезервированные символы остаются закодированными. В предыдущих версиях .NET Framework они декодировались.</li></ul>|
|Предложение|Для приложений, предназначенных для версий платформы .NET Framework, начиная с 4.7.2, новое поведение декодирования включено по умолчанию. Если это изменение нежелательно, можно отключить его, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Для приложений, предназначенных для более ранних версий .NET Framework, но выполняемых в версиях начиная с .NET Framework 4.7.2, новое поведение декодирования отключено по умолчанию. Вы можете включить это изменение, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|

