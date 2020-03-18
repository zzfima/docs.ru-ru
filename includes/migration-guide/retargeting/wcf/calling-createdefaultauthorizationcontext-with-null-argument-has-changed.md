---
ms.openlocfilehash: 9ec5fa379556dedeaa7a35e34f004340ab47a39c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804400"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>Был изменен вызов метода CreateDefaultAuthorizationContext с аргументом NULL

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.6 изменилась реализация <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=name>, возвращаемая вызовом к <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=name> с нулевым аргументом authorizationPolicies.|
|Предложение|В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении. В таких случаях прежнее поведение можно восстановить двумя способами.<ol><li>Перекомпилируйте приложение для ориентации на версию .NET Framework, предшествующую 4.6. Для служб, размещенных в IIS, используйте элемент &lt;httpRuntime targetFramework=&quot;x.x&quot; /&gt; для выбора более ранней версии .NET Framework в качестве целевой платформы.</li><li>Добавьте следующую строку в раздел <code>&lt;appSettings&gt;</code> файла app.config: <code>&lt;add key=&quot;appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext&quot; value=&quot;true&quot; /&gt;</code>.</li></ol>|
|Область|Дополнительный номер|
|Version|4.6|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType></li></ul>|
