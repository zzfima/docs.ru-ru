---
title: Оператор &lt;&lt; (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 036acd6159bcf5ca1677ee6383c9db357625cd67
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276814"
---
# <a name="ltlt-operator-c-reference"></a>Оператор &lt;&lt; (справочник по C#)
Оператор сдвига влево (`<<`) сдвигает первый операнд влево на число битов, задаваемое вторым операндом. Второй операнд должен иметь тип [int](../../../csharp/language-reference/keywords/int.md) или тип, для которого существует предварительно определенное неявное числовое преобразование в `int`.  
  
## <a name="remarks"></a>Примечания  
 Если первый операнд имеет тип [int](../../../csharp/language-reference/keywords/int.md) или [uint](../../../csharp/language-reference/keywords/uint.md) (32-разрядное число), величина сдвига определяется пятью младшими разрядами второго операнда. Фактическая величина сдвига составляет от 0 до 31 бита.  
  
 Если первый операнд имеет тип [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-разрядное число), величина сдвига определяется шестью младшими разрядами второго операнда. Фактическая величина сдвига составляет от 0 до 63 битов.  
  
 Любые старшие разряды, не попадающие в диапазон значений типа первого операнда после сдвига, отбрасываются, а пустые младшие разряды заполняются нулями. Операции сдвига никогда не вызывают переполнение.  
  
 Определяемые пользователем типы могут перегружать оператор `<<` (см. [operator](../../../csharp/language-reference/keywords/operator.md)). В этом случае первый операнд должен иметь определяемый пользователем тип, а второй операнд — тип `int`. При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]  
  
## <a name="comments"></a>Комментарии  
 Обратите внимание, что `i<<1` и `i<<33` дают один и тот же результат, поскольку 1 и 33 имеют одинаковые младшие пять разрядов.  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
