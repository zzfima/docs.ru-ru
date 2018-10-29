---
title: Таблица неявных числовых преобразований (Справочник по C#)
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: c3c0153a0ae3e07839822c8bb978b1a09277bd53
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188707"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Таблица неявных числовых преобразований (Справочник по C#)

В следующей таблице приведены предопределенные неявные преобразования между числовыми типами .NET.
  
|Исходный тип|Кому|  
|----------|--------|  
|[sbyte](sbyte.md)|`short`, `int`, `long`, `float`, `double` или `decimal`|  
|[byte](byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[short](short.md)|`int`, `long`, `float`, `double` или `decimal`|  
|[ushort](ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[int](int.md)|`long`, `float`, `double` или `decimal`|  
|[uint](uint.md)|`long`, `ulong`, `float`, `double` или `decimal`|  
|[long](long.md)|`float`, `double`или `decimal`|  
|[char](char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[float](float.md)|`double`|  
|[ulong](ulong.md)|`float`, `double`или `decimal`|  
  
## <a name="remarks"></a>Примечания  

- Любой [целочисленный тип](integral-types-table.md) неявно преобразуется к любому [типу с плавающей запятой](floating-point-types-table.md).

- При преобразовании из `int`, `uint`, `long` или `ulong` в `float` и из `long` или `ulong` в `double` может быть потеряна точность, но не величина.  
  
- Не поддерживается неявное преобразование в тип `char`.  
  
- Не поддерживается неявное преобразование между типами `float` и `double` и типом `decimal`.  
  
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
