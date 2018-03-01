---
title: "Оператор &amp;= (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bea90651faaafe7b754ce1cf16bddbab997d5f5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
