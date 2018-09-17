---
title: Таблица явных числовых преобразований (Справочник по C#)
ms.date: 09/06/2018
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 22bb2117e7b78596e1fb6af63584f51b066564c9
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45594552"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Таблица явных числовых преобразований (Справочник по C#)

В следующей таблице показаны предопределенные явные преобразования между числовыми типами .NET, для которых нет [неявного преобразования](implicit-numeric-conversions-table.md).

|Исходный тип|Кому|  
|----------|--------|  
|[sbyte](sbyte.md)|`byte`, `ushort`, `uint`, `ulong` или `char`|  
|[byte](byte.md)|`sbyte` или `char`|  
|[short](short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` или `char`|  
|[ushort](ushort.md)|`sbyte`, `byte`, `short` или `char`|  
|[int](int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` или `char`|  
|[uint](uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` или `char`|  
|[long](long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` или `char`|  
|[ulong](ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` или `char`|  
|[char](char.md)|`sbyte`, `byte`или `short`|  
|[float](float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` или `decimal`|  
|[double](double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` или `decimal`|  
|[decimal](decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` или `double`|  
  
## <a name="remarks"></a>Примечания  
  
- Явное числовое преобразование может привести к потере точности или возникновению исключения, обычно <xref:System.OverflowException>.  

- При преобразовании значения целочисленного типа в другой целочисленный тип результат зависит от переполнения [контекста проверки](checked-and-unchecked.md). В проверенном контексте преобразование выполняется успешно, если исходное значение находится в диапазоне конечного типа. В противном случае возникает исключение <xref:System.OverflowException>. В непроверяемом контексте преобразование всегда завершается успешно и выполняется следующим образом.

  - Если исходный тип больше целевого, исходное значение усекается путем отбрасывания его "лишних" самых значимых битов. Результат затем обрабатывается как значение целевого типа.

  - Если исходный тип меньше целевого, исходное значение дополняется знаками или нулями, чтобы иметь тот же размер, что и целевой тип. Знаки добавляются, если исходный тип имеет знак. Если у исходного типа нет знака, добавляются нули. Результат затем обрабатывается как значение целевого типа.

  - Если исходный тип совпадает по размеру с целевым, исходное значение обрабатывается как значение целевого типа.
  
- При преобразовании значения `decimal` в целочисленный тип оно округляется в сторону нуля до ближайшего целого значения. Если итоговое целое значение находится вне диапазона целевого типа, возникает исключение <xref:System.OverflowException>.  
  
- При преобразовании значения `double` или `float` в целочисленный тип оно округляется в сторону нуля до ближайшего целого значения. Если полученное целое значение выходит за пределы диапазона целевого типа, результат будет зависеть от [контекста проверки](checked-and-unchecked.md) переполнения. В проверенном контексте возникает исключение <xref:System.OverflowException>, а в непроверенном контексте результатом будет неопределенное значение целевого типа.  
  
- При преобразовании из `double` в `float` значение `double` округляется до ближайшего значения `float`. Если значение `double` слишком мало или слишком велико для целевого типа, результатом будет ноль или бесконечность соответственно.  
  
- При преобразовании из `float` или `double` в `decimal` исходное значение преобразуется в представление `decimal` и при необходимости округляется до ближайшего числа после 28-го десятичного разряда. В зависимости от исходного значения возможны следующие результаты:  

  - Если исходное значение слишком мало для представления в виде `decimal`, результатом будет ноль.  

  - Если исходное значение не является числом (NaN), равно бесконечности или слишком велико для представления в виде `decimal`, возникает исключение <xref:System.OverflowException>.  
  
- При преобразовании из `decimal` в `float` или `double` значение `decimal` округляется до ближайшего значения `double` или `float`.  
  
 Дополнительные сведения о явных преобразованиях см. в разделе [Явные преобразования](/dotnet/csharp/language-reference/language-specification/conversions#explicit-conversions) в [спецификации языка C#](../language-specification/index.md).
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Приведение и преобразование типов](../../programming-guide/types/casting-and-type-conversions.md)
- [Оператор ()](../operators/invocation-operator.md)
- [Таблица целых типов](integral-types-table.md)
- [Таблица типов с плавающей запятой](floating-point-types-table.md)
- [Таблица встроенных типов](built-in-types-table.md)
- [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md)
