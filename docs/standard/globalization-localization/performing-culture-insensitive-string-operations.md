---
title: "Выполнение строковых операций, не зависящих от языка и региональных параметров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e703e9adc531b7d1695d3e9bbed61a2c0f62ad31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="performing-culture-insensitive-string-operations"></a>Выполнение строковых операций, не зависящих от языка и региональных параметров
Большинство методов .NET Framework, выполняющих строковые операции с учетом языка и региональных параметров по умолчанию предоставляют перегрузки метода, которые позволяют явным образом указать язык и региональные параметры путем передачи <xref:System.Globalization.CultureInfo> параметра. Эти перегрузки позволяют устранить различия в сопоставлении регистров и правилах сортировки, вызванные различием языка и региональных параметров, и получить результаты, которые не зависят от языка и региональных параметров.  
  
 В этом разделе содержатся следующие подразделы, которые показывают, как выполнять операции со строками без учета языка и региональных параметров с помощью методов платформы .NET Framework, которые по умолчанию учитывают язык и региональные параметры.  
  
## <a name="in-this-section"></a>Содержание  
 [Сравнение строк без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Описывает использование <xref:System.String.Compare%2A?displayProperty=nameWithType> и <xref:System.String.CompareTo%2A?displayProperty=nameWithType> методы для выполнения сравнения строк без учета языка и региональных параметров.  
  
 [Изменение регистра без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Описывает использование <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, и <xref:System.Char.ToLower%2A?displayProperty=nameWithType> методы для выполнения смены регистра независимо от языка и региональных параметров.  
  
 [Выполнение строковых операций без учета языка и региональных параметров в коллекциях](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Описывает использование <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> класса <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> и <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> для выполнения операций без учета языка и региональных параметров в коллекции.  
  
 [Выполнение строковых операций без учета языка и региональных параметров в массивах](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Описывает использование <xref:System.Array.Sort%2A?displayProperty=nameWithType> и <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> методы для выполнения операций без учета языка и региональных параметров в массивах.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Операции со строками без учета языка и региональных параметров](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Описывает, почему следует иметь в виду язык и региональные параметры при выполнении операций над строками, и содержит указания о том, когда следует выполнять операции с учетом и без учета языка и региональных параметров.
