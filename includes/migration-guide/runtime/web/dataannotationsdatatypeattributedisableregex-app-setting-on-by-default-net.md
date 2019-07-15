---
ms.openlocfilehash: b021de74509b6d9ba77678d3105e0f7bb406f79d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67856970"
---
### <a name="dataannotationsdatatypeattributedisableregex-app-setting-is-on-by-default-in-net-framework-472"></a>Параметр приложения "dataAnnotations:dataTypeAttribute:disableRegEx" по умолчанию включен в .NET Framework 4.7.2

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.6.1 появился новый параметр приложения (<code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code>), который позволяет пользователям отключать регулярные выражения в атрибутах типов данных (таких как <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>, <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType> и <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType>). Это помогает сделать приложения менее уязвимыми, в частности для атак типа "отказ в обслуживании" с использованием определенных регулярных выражений.<br/>В .NET Framework 4.6.1 этот параметр, запрещающий использование RegEx, по умолчанию имел значение <code>false</code>. Начиная с версии .NET Framework 4.7.2, эта настройка по умолчанию переведена в значение <code>true</code>, что обеспечивает дополнительную защиту от уязвимостей для приложений, разрабатываемых с использованием .NET Framework 4.7.2.|
|Предложение|Если после перехода на версию .NET Framework 4.7.2 вы обнаружите, что регулярные выражения в вашем веб-приложении перестали работать, вы можете изменить значение <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> на <code>false</code> и вернуться к предыдущему режиму работы.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot; value=&quot;false&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7.2|
|Тип|Среда выполнения|

