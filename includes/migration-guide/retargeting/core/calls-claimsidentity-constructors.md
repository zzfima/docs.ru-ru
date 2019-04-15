---
ms.openlocfilehash: 6dd7f2a2f6dec306940650beee58104b20788bdb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235006"
---
### <a name="calls-to-claimsidentity-constructors"></a>Вызовы к конструкторам ClaimsIdentity

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.6.2 конструкторы <xref:System.Security.Claims.ClaimsIdentity> с параметром <xref:System.Security.Principal.IIdentity?displayProperty=name> иначе задают свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name>. Если аргумент <xref:System.Security.Principal.IIdentity?displayProperty=name> является объектом <xref:System.Security.Claims.ClaimsIdentity>, а свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> этого объекта <xref:System.Security.Claims.ClaimsIdentity> не равно <code>null</code>, свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> присоединяется с помощью метода <xref:System.Security.Claims.ClaimsIdentity.Clone>. В Framework 4.6.1 и более ранних версиях свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> прикреплено как существующая ссылка. В результате этого изменения, начиная с .NET Framework 4.6.2, свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> нового объекта <xref:System.Security.Claims.ClaimsIdentity> не равно свойству <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> аргумента конструктора <xref:System.Security.Principal.IIdentity?displayProperty=name>. В .NET Framework 4.6.1 и более ранних версиях они равны.|
|Предложение|Если такое поведение нежелательно, можно восстановить прежнее поведение, задав переключателю <code>Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity</code> в файле конфигурации приложения значение <code>true</code>. Для этого требуется добавить следующую информацию в раздел <code>&lt;runtime&gt;</code> файла web.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)?displayProperty=nameWithType></li><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})?displayProperty=nameWithType></li><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)?displayProperty=nameWithType></li></ul>|
