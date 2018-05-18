---
title: Оператор &gt;&gt;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 41203f6e7c9929bb349d29c40cf7cc6c24550c36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-c-reference"></a>Оператор &gt;&gt;= (справочник по C#)
Оператор присваивания сдвига вправо.  
  
## <a name="remarks"></a>Примечания  
 Выражение в формате  
  
```  
x >>= y  
```  
  
 вычисляется как  
  
```  
x = x >> y  
```  
  
 за исключением того, что `x` вычисляется только один раз. [Оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.  
  
 Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
