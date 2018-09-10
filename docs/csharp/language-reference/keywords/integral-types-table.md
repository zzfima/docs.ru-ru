---
title: Таблица целочисленных типов (справочник по C#)
description: Общие сведения о встроенных целочисленных типах в C#
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: 4ac16d185a52cdb03fcb22f57ebf7506f2fb2745
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078852"
---
# <a name="integral-types-table-c-reference"></a>Таблица целочисленных типов (справочник по C#)

В следующей таблице приводятся сведения о размерах и диапазонах для целочисленных типов, которые составляют подмножество простых типов.  
  
|Тип|Диапазон|Размер|  
|----------|-----------|----------|  
|[sbyte](sbyte.md)|От -128 до 127|8-разрядное целое число со знаком|  
|[byte](byte.md)|От 0 до 255|8-разрядное целое число без знака|  
|[char](char.md)|От U+0000 до U+ffff|Символ Юникода (16-разрядный)|  
|[short](short.md)|От -32 768 до 32 767|16-разрядное целое число со знаком|  
|[ushort](ushort.md)|От 0 до 65 535|16-разрядное целое число без знака|  
|[int](int.md)|От -2 147 483 648 до 2 147 483 647|32-разрядное целое число со знаком|  
|[uint](uint.md)|От 0 до 4 294 967 295|32-разрядное целое число без знака|  
|[long](long.md)|От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807|64-разрядное целое число со знаком|  
|[ulong](ulong.md)|От 0 до 18 446 744 073 709 551 615|64-разрядное целое число без знака|  

## <a name="remarks"></a>Примечания
  
Если значение, представленное целочисленным литералом, превышает <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, происходит ошибка компиляции [CS1021](../../misc/cs1021.md).

Используйте класс <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, чтобы представить произвольно большое целое число со знаком.
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Справочные таблицы по типам](reference-tables-for-types.md)
- [Таблица типов с плавающей запятой](floating-point-types-table.md)
- [Таблица значений по умолчанию](default-values-table.md)
- [Таблица форматирования числовых результатов](formatting-numeric-results-table.md)
- [Таблица встроенных типов](built-in-types-table.md)
