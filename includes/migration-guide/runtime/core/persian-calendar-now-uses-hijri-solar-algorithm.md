---
ms.openlocfilehash: bfe406161ac754124a2cc38c68a80c3b9fb2c7f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858408"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>Теперь в персидском календаре используется алгоритм солнечного календаря хиджры

|   |   |
|---|---|
|Подробнее|Начиная с .NET Framework 4.6 класс <xref:System.Globalization.PersianCalendar?displayProperty=name> использует алгоритм солнечного календаря хиджры. Начиная с .NET Framework 4.6 при преобразовании дат между <xref:System.Globalization.PersianCalendar?displayProperty=name> и другими календарями может быть получен немного другой результат для дат, ранее 1800 г. или позднее 2023 г. (по григорианскому календарю). Кроме того, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> теперь <code>March 22, 0622</code> вместо <code>March 21, 0622</code>.|
|Предложение|Имейте в виду, что при использовании персидского календаря в .NET Framework 4.6 некоторые даты в прошлом или будущем могут несколько отличаться. Кроме того, даты, сериализуемые между процессами, которые могут выполняться в различных версиях .NET Framework, не следует хранить в виде строк дат персидского календаря (поскольку эти значения могут быть разными).|
|Область|Дополнительный номер|
|Version|4.6|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
