---
title: Оператор &amp;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: a749cf2f73faa80df49699b1e466cde290ed386e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="amp-operator-c-reference"></a>Оператор &amp;= (справочник по C#)
Оператор присваивания И.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `&=`, такое как  
  
```  
x &= y  
```  
  
 эквивалентно  
  
```  
x = x & y  
```  
  
 за исключением того, что `x` вычисляется только один раз. [Оператор &](../../../csharp/language-reference/operators/and-operator.md) выполняет побитовую логическую операцию И в отношении целочисленных операндов и логическую операцию И в отношении операндов типа `bool`.  
  
 Оператор `&=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать бинарный [оператор &](../../../csharp/language-reference/operators/and-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
