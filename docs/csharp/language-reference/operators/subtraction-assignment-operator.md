---
title: Оператор -= (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 7cade0811536d836480f80a56cf8c4d09e089a0b
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43773994"
---
# <a name="--operator-c-reference"></a>Оператор -= (Справочник по C#)
Оператор присваивания вычитания.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `-=`, такое как  
  
```csharp  
x -= y  
```  
  
 эквивалентно  
  
```csharp  
x = x - y  
```  
  
 за исключением того, что `x` вычисляется только один раз. Значение [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) зависит от типов `x` и `y` (вычитание для числовых операндов, удаление делегатов для операндов делегатов и т. д.).  
  
 Оператор `-=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
 Оператор -= также используется в C# для отмены подписки на событие. Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
