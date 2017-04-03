---
title: "Оператор -= (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- -=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d9ffcfe9b42f7ca65801a58338c8e40a37c90316
ms.lasthandoff: 03/13/2017

---
# <a name="--operator-c-reference"></a>Оператор -= (Справочник по C#)
Оператор присваивания вычитания.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `-=`, такое как  
  
```  
x -= y  
```  
  
 эквивалентно  
  
```  
x = x - y  
```  
  
 за исключением того, что `x` вычисляется только один раз. Значение [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) зависит от типов `x` и `y` (вычитание для числовых операндов, удаление делегатов для операндов делегатов и т. д.).  
  
 Оператор `-=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
 Оператор -= также используется в C# для отмены подписки на событие. Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

