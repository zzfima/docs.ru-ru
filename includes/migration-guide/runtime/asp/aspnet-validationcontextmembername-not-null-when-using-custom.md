---
ms.openlocfilehash: 3b94c88809513e31a5f226bcfce39abbfa4de378
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70017376"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET ValidationContext.MemberName не имеет значения NULL при использовании пользовательского DataAnnotations.ValidationAttribute

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7.2 и более ранних версий при использовании пользовательского <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> свойство <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> возвращает <code>null</code>.  В .NET Framework 4.8 он возвращает имя члена.|
|Предложение|Чтобы восстановить прежнее поведение, добавьте следующий параметр в файл конфигурации приложения:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Это поведение будет изменено в предстоящем выпуске службы, и вам потребуется явно выбрать новое поведение. Свойство будет возвращать значение, отличное от NULL, для пользовательского атрибута `ValidationAttribute`, если параметр `aspnet:GetValidationMemberName` имеет значение `true`.|
|Область|Неизвестно|
|Версия|4.8|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
