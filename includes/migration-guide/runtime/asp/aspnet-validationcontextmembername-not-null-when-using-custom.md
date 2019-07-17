---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802609"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET ValidationContext.MemberName не имеет значения NULL при использовании пользовательского DataAnnotations.ValidationAttribute

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7.2 и более ранних версий при использовании пользовательского <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> свойство <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> возвращает <code>null</code>.  В .NET Framework 4.8 он возвращает имя члена.|
|Предложение|Поведение по умолчанию свойства <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> остается неизменным.  Для получения допустимого значения из свойства <code>ValidationContext.MemberName</code> добавьте в файл конфигурации приложения следующий параметр:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Неизвестно|
|Версия|4.8|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

