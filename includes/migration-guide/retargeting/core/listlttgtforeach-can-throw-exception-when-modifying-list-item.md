---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234840"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a>List\<T>.ForEach может создавать исключение при изменении элемента списка

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5 перечислитель <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> будет создавать исключение <xref:System.InvalidOperationException?displayProperty=name> при изменении элемента в вызывающей коллекции. Ранее исключение не создавалось, но могли возникать конфликты.|
|Предложение|В идеальном случае следует исправить код, чтобы он не изменял списки при перечислении их элементов, поскольку эта операция небезопасна. Чтобы вернуться к предыдущему поведению, приложение должно быть предназначено для платформы .NET Framework 4.0.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
