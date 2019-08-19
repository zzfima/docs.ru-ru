---
title: Справочник по C#. Таблица явных числовых преобразований
ms.custom: seodec18
ms.date: 09/06/2018
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 4dee46d075ea3d45d53ac0f64b539231188cf867
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566316"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Таблица явных числовых преобразований (Справочник по C#)

В следующей таблице показаны предопределенные явные преобразования между числовыми типами .NET, для которых нет [неявного преобразования](implicit-numeric-conversions-table.md).

|Исходный тип|Кому|  
|----------|--------|  
|[sbyte](../builtin-types/integral-numeric-types.md)|`byte`, `ushort`, `uint`, `ulong` или `char`|  
|[byte](../builtin-types/integral-numeric-types.md)|`sbyte` или `char`|  
|[short](../builtin-types/integral-numeric-types.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` или `char`|  
|[ushort](../builtin-types/integral-numeric-types.md)|`sbyte`, `byte`, `short` или `char`|  
|[int](../builtin-types/integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` или `char`|  
|[uint](../builtin-types/integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int` или `char`|  
|[long](../builtin-types/integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` или `char`|  
|[ulong](../builtin-types/integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` или `char`|  
|[char](char.md)|`sbyte`, `byte`или `short`|  
|[float](../builtin-types/floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` или `decimal`|  
|[double](../builtin-types/floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` или `decimal`|  
|[decimal](../builtin-types/floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` или `double`|  
  
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
  
 Дополнительные сведения о явных преобразованиях см. в разделе [Явные преобразования](~/_csharplang/spec/conversions.md#explicit-conversions) в [спецификации языка C#](../language-specification/index.md).
  
## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Приведение и преобразование типов](../../programming-guide/types/casting-and-type-conversions.md)
- [Оператор ()](../operators/type-testing-and-cast.md#cast-operator-)
- [Целочисленные типы](../builtin-types/integral-numeric-types.md)
- [Таблица типов с плавающей запятой](../builtin-types/floating-point-numeric-types.md)
- [Таблица встроенных типов](built-in-types-table.md)
- [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md)
