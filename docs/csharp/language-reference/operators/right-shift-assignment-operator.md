---
title: Оператор &gt;&gt;= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: f2bac6a4320980d80a9b6c2597dcf8dc6f08ac70
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865027"
---
# <a name="gtgt-operator-c-reference"></a>Оператор &gt;&gt;= (справочник по C#)
Оператор присваивания сдвига вправо.  
  
## <a name="remarks"></a>Примечания  
 Выражение в формате  
  
```csharp  
x >>= y  
```  
  
 вычисляется как  
  
```csharp  
x = x >> y  
```  
  
 за исключением того, что `x` вычисляется только один раз. [Оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.  
  
 Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](../../../csharp/language-reference/operators/right-shift-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
