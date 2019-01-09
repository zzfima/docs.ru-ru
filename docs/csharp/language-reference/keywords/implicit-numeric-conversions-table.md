---
title: Справочник по C#. Таблица неявных числовых преобразований
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: ab6506e619c675ddd68237c4ddca870e9e14098f
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058468"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Таблица неявных числовых преобразований (Справочник по C#)

В следующей таблице приведены предопределенные неявные преобразования между числовыми типами .NET.
  
|Исходный тип|Кому|  
|----------|--------|  
|[sbyte](sbyte.md)|`short`, `int`, `long`, `float`, `double` или `decimal`|  
|[byte](byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[char](char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[short](short.md)|`int`, `long`, `float`, `double` или `decimal`|  
|[ushort](ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[int](int.md)|`long`, `float`, `double` или `decimal`|  
|[uint](uint.md)|`long`, `ulong`, `float`, `double` или `decimal`|  
|[long](long.md)|`float`, `double`или `decimal`|  
|[ulong](ulong.md)|`float`, `double`или `decimal`|  
|[float](float.md)|`double`|  
  
## <a name="remarks"></a>Примечания  

- Любой [целочисленный тип](integral-types-table.md) неявно преобразуется к любому [типу с плавающей запятой](floating-point-types-table.md).

- При преобразовании из `int`, `uint`, `long` или `ulong` в `float` и из `long` или `ulong` в `double` может быть потеряна точность, но не величина.  
  
- Не поддерживается неявное преобразование в типы `char`, `byte` и `sbyte`.  

- Не поддерживается неявное преобразование из типов `char`, `double` и `decimal`.
  
- Не поддерживается неявное преобразование между типом `decimal` и типами `float` или `double`.  
  
- Значение константного выражения типа `int` (например, значение, представленное целочисленным литералом) может быть преобразовано в `sbyte`, `byte`, `short`, `ushort`, `uint` или `ulong`, если оно находится в диапазоне конечного типа.

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

Дополнительные сведения о неявных преобразованиях см. в разделе [Неявные преобразования](~/_csharplang/spec/conversions.md#implicit-conversions) в [спецификации языка C#](../language-specification/index.md).
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Таблица целых типов](integral-types-table.md)
- [Таблица типов с плавающей запятой](floating-point-types-table.md)
- [Таблица встроенных типов](built-in-types-table.md)
- [Таблица явных числовых преобразований](explicit-numeric-conversions-table.md)
- [Приведение и преобразование типов](../../programming-guide/types/casting-and-type-conversions.md)
