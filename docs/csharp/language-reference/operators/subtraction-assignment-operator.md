---
title: Справочник по C#. Оператор -=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: dc3cedafc57e1c6ec9bc34ca4e2c2aa9c604848c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239589"
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
  
 Оператор -= также используется в C# для отмены подписки на событие. Дополнительные сведения см. в разделе [Как подписке и отмене подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
