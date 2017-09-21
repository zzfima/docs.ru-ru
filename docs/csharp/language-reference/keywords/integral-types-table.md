---
title: "Таблица целых типов (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
caps.latest.revision: 9
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
ms.openlocfilehash: a2932d0b7c8e1b01a4965b29d90bdd5711ddb5dc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="integral-types-table-c-reference"></a>Таблица целых типов (Справочник по C#)
В следующей таблице приводятся сведения о размерах и диапазонах для целочисленных типов, которые составляют подмножество простых типов.  
  
|Тип|Диапазон|Размер|  
|----------|-----------|----------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|От -128 до 127|8-разрядное целое число со знаком|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|От 0 до 255|8-разрядное целое число без знака|  
|[char](../../../csharp/language-reference/keywords/char.md)|От U+0000 до U+ffff|Символ Юникода (16-разрядный)|  
|[short](../../../csharp/language-reference/keywords/short.md)|От -32 768 до 32 767|16-разрядное целое число со знаком|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|От 0 до 65 535|16-разрядное целое число без знака|  
|[int](../../../csharp/language-reference/keywords/int.md)|От -2 147 483 648 до 2 147 483 647|32-разрядное целое число со знаком|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|От 0 до 4 294 967 295|32-разрядное целое число без знака|  
|[long](../../../csharp/language-reference/keywords/long.md)|От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807|64-разрядное целое число со знаком|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|От 0 до 18 446 744 073 709 551 615|64-разрядное целое число без знака|  
  
 Если значение, представленное целочисленным литералом, выходит за пределы диапазона значений типа `ulong`, происходит ошибка компиляции.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица типов с плавающей запятой](../../../csharp/language-reference/keywords/floating-point-types-table.md)   
 [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)   
 [Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
