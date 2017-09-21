---
title: "Оператор &lt;&lt; (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 18
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
ms.openlocfilehash: 4e6ad17232ec4eb087ca300342331af6a30789b1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a>Оператор &lt;&lt; (справочник по C#)
Оператор сдвига влево (`<<`) сдвигает первый операнд влево на число битов, задаваемое вторым операндом. Второй операнд должен иметь тип [int](../../../csharp/language-reference/keywords/int.md) или тип, для которого существует предварительно определенное неявное числовое преобразование в `int`.  
  
## <a name="remarks"></a>Примечания  
 Если первый операнд имеет тип [int](../../../csharp/language-reference/keywords/int.md) или [uint](../../../csharp/language-reference/keywords/uint.md) (32-разрядное число), величина сдвига определяется пятью младшими разрядами второго операнда. Фактическая величина сдвига составляет от 0 до 31 бита.  
  
 Если первый операнд имеет тип [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-разрядное число), величина сдвига определяется шестью младшими разрядами второго операнда. Фактическая величина сдвига составляет от 0 до 63 битов.  
  
 Любые старшие разряды, не попадающие в диапазон значений типа первого операнда после сдвига, отбрасываются, а пустые младшие разряды заполняются нулями. Операции сдвига никогда не вызывают переполнение.  
  
 Определяемые пользователем типы могут перегружать оператор `<<` (см. [operator](../../../csharp/language-reference/keywords/operator.md)). В этом случае первый операнд должен иметь определяемый пользователем тип, а второй операнд — тип `int`. При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]  
  
## <a name="comments"></a>Комментарии  
 Обратите внимание, что `i<<1` и `i<<33` дают один и тот же результат, поскольку 1 и 33 имеют одинаковые младшие пять разрядов.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

