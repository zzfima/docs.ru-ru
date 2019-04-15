---
ms.openlocfilehash: efa0efaf40e2e432d477f1659d7bde3abc98241d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236105"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Теперь поддерживаются категории стандартной версии Юникода 8.0

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.6.2 данные Юникода были обновлены со стандартной версии 6.3 до версии 8.0.  При запросе категорий символов Юникода в .NET Framework 4.6.2 некоторые результаты могут не соответствовать результатам в предыдущих версиях .NET Framework.  Это изменение в первую очередь влияет на слоги языка чероки, а также знаки гласных и обозначения тонов в новой письменности Тай-Лю.|
|Предложение|Просмотрите код и удалите или измените логику, зависящую от жестко заданных категорий символов Юникода.|
|Область|Дополнительный номер|
|Версия|4.6.2|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
