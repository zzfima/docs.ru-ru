---
title: Выполнение строковых операций, не зависящих от языка и региональных параметров
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
ms.openlocfilehash: 183078b1f7a3eb3530fea8af06dbb59055d7d25d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120789"
---
# <a name="performing-culture-insensitive-string-operations"></a>Выполнение строковых операций, не зависящих от языка и региональных параметров
Большинство методов .NET Framework, которые выполняют операции со строками с учетом языка и региональных параметров, по умолчанию предоставляют перегрузки, позволяющие явно указать используемые язык и региональные параметры, указав соответствующий параметр <xref:System.Globalization.CultureInfo>. Эти перегрузки позволяют устранить различия в сопоставлении регистров и правилах сортировки, вызванные различием языка и региональных параметров, и получить результаты, которые не зависят от языка и региональных параметров.  
  
 В этом разделе содержатся следующие подразделы, которые показывают, как выполнять операции со строками без учета языка и региональных параметров с помощью методов платформы .NET Framework, которые по умолчанию учитывают язык и региональные параметры.  
  
## <a name="in-this-section"></a>Содержание раздела  
 [Сравнение строк без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Описывает использование методов <xref:System.String.Compare%2A?displayProperty=nameWithType> и <xref:System.String.CompareTo%2A?displayProperty=nameWithType> для сравнения строк без учета языка и региональных параметров.  
  
 [Изменение регистра без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Описывает использование методов <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> и <xref:System.Char.ToLower%2A?displayProperty=nameWithType> для изменения регистра символов без учета языка и региональных параметров.  
  
 [Выполнение строковых операций без учета языка и региональных параметров в коллекциях](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Описывает использование <xref:System.Collections.CaseInsensitiveComparer>, класса <xref:System.Collections.CaseInsensitiveHashCodeProvider>, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> и <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> для сравнения коллекций без учета языка и региональных параметров.  
  
 [Выполнение строковых операций без учета языка и региональных параметров в массивах](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Описывает использование методов <xref:System.Array.Sort%2A?displayProperty=nameWithType> и <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> для операций над массивами без учета языка и региональных параметров.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Операции со строками без учета языка и региональных параметров](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Описывает, почему следует иметь в виду язык и региональные параметры при выполнении операций над строками, и содержит указания о том, когда следует выполнять операции с учетом и без учета языка и региональных параметров.

## <a name="see-also"></a>См. также

- [Таблицы весовых коэффициентов сортировки (для .NET в ОС Windows)](https://www.microsoft.com/download/details.aspx?id=10921)
- [Таблица параметров сортировки по умолчанию для элементов Юникод (для .NET Core в Linux и macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
