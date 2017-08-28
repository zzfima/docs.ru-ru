---
title: "Таблица явных числовых преобразований (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0315810522be319a6bb565c99e1c8f7d1ba4701b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Таблица явных числовых преобразований (Справочник по C#)
Явное числовое преобразование используется для преобразования любого числового типа в любой другой числовой тип, для которого отсутствует неявное преобразование, с использованием выражения приведения. Эти преобразования показаны в следующей таблице.  
  
 Дополнительные сведения о преобразованиях см. в разделе [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
|Исходный тип|Целевой тип|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`byte`, `ushort`, `uint`, `ulong` или `char`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`Sbyte` или `char`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` или `char`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`sbyte`, `byte`, `short` или `char`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` или `char`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` или `char`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` или `char`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` или `char`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`sbyte`, `byte`или `short`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` или `decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` или `decimal`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` или `double`|  
  
## <a name="remarks"></a>Примечания  
  
-   Явное числовое преобразование может привести к потере точности или возникновению исключения.  
  
-   При преобразовании значения `decimal` в целочисленный тип оно округляется в сторону нуля до ближайшего целого значения. Если итоговое целое значение находится вне диапазона целевого типа, возникает исключение <xref:System.OverflowException>.  
  
-   При преобразовании значения `double` или `float` в целочисленный тип это значение усекается. Если полученное целое значение выходит за пределы диапазона целевого значения, результат будет зависеть от контекста проверки переполнения. В проверенном контексте возникает исключение `OverflowException`, а в непроверенном контексте результатом будет неопределенное значение целевого типа.  
  
-   При преобразовании из `double` в `float` значение `double` округляется до ближайшего значения `float`. Если значение `double` слишком мало или слишком велико для целевого типа, результатом будет ноль или бесконечность соответственно.  
  
-   При преобразовании из `float` или `double` в `decimal` исходное значение преобразуется в представление `decimal` и при необходимости округляется до ближайшего числа после 28-го десятичного разряда. В зависимости от исходного значения возможны следующие результаты:  
  
    -   Если исходное значение слишком мало для представления в виде `decimal`, результатом будет ноль.  
  
    -   Если исходное значение не является числом (NaN), равно бесконечности или слишком велико для представления в виде `decimal`, возникает исключение `OverflowException`.  
  
-   При преобразовании из `decimal` в `float` или `double` значение `decimal` округляется до ближайшего значения `double` или `float`.  
  
 Дополнительные сведения о явных преобразованиях см. в спецификации языка C#. Дополнительные сведения о доступе к спецификации см. в разделе [Спецификация языка C#](../../../csharp/language-reference/language-specification/index.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Оператор ()](../../../csharp/language-reference/operators/invocation-operator.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)

