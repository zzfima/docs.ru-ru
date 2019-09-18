---
ms.openlocfilehash: 841cb06bf94844d9f4da9dc33e60bad0d43dcd84
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70997702"
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
