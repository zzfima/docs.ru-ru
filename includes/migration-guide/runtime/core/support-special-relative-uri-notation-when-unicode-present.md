---
ms.openlocfilehash: 34d7395e72f6ef252ac68366bcd346cd8d464036
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59236150"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Поддержка нотации специального относительного URI при наличии символов Юникода

|   |   |
|---|---|
|Подробные сведения|<xref:System.Uri> больше не будет создавать исключение <xref:System.NullReferenceException> при вызове <xref:System.Uri.TryCreate%2A> для определенных относительных URI, содержащих символы Юникода. Простое воспроизведение <xref:System.NullReferenceException> представлено ниже (с двумя эквивалентными инструкциями):<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Для воспроизведения <xref:System.NullReferenceException> должны выполняться следующие условия:<ul><li>URI должен быть указан как относительный: с префиксом "http:", за которым не следуют две косые черты "//".</li><li>URI должен содержать незарезервированные символы или символы Юникода, закодированные процентами.</li></ul>|
|Предложение|Пользователям, зависящим от этого поведения, для запрета относительных URI следует указывать <xref:System.UriKind.Absolute?displayProperty=nameWithType> при создании URI.|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
