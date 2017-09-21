---
title: "Оператор &amp;= (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
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
ms.openlocfilehash: 6dec8de5077c07150ea37b88979e7b59b231d610
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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
 [!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

