---
ms.openlocfilehash: 6c2c6422ca4d426fcc2ff5827a2387abb5578e3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234833"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>Синтаксический анализ System.Uri соответствует стандарту RFC 3987

|   |   |
|---|---|
|Подробные сведения|Синтаксический анализ URI претерпел ряд изменений в .NET Framework 4.5. Обратите внимание, что эти изменения касаются только кода, предназначенного для .NET Framework 4.5. Если двоичный файл предназначен для .NET Framework 4.0, будет действовать старое поведение. В синтаксический анализ URI в .NET Framework 4.5 внесены следующие изменения:<ul><li>Синтаксический анализ URI будет выполнять проверку нормализации и символов в соответствии с последними правилами IRI стандарта RFC 3987.</li><li>Форма нормализации Юникода C будет выполняться только в части узла URI.</li><li>Недопустимые URI mailto: теперь будут вызывать исключение.</li><li>Конечные точки в конце сегмента пути теперь сохраняются.</li><li>Идентификаторы URI <code>file://</code> не экранируют символ <code>?</code>.</li><li>Управляющие символы Юникода с <code>U+0080</code> по <code>U+009F</code> не поддерживаются.</li><li>Символы запятой <code>,</code> или <code>%2c</code> не отменяются автоматически.</li></ul>|
|Предложение|Если необходимы старые семантики синтаксического анализа URI в .NET Framework 4.0 (часто они не требуются), их можно использовать, нацелив приложение на .NET Framework 4.0. Это можно сделать с помощью <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> в сборке или в пользовательском интерфейсе системы проектов Visual Studio на странице свойств проекта.|
|Область|Значительно|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Uri.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.UriKind)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.Uri,System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li></ul>|
