---
title: Оператор /= (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a>Оператор /= (Справочник по C#)
Оператор присваивания деления.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `/=`, такое как  
  
```csharp  
x /= y  
```  
  
 эквивалентно  
  
```csharp  
x = x / y  
```  
  
 за исключением того, что `x` вычисляется только один раз. В числовых типах [оператор /](../../../csharp/language-reference/operators/division-operator.md) используется для выполнения операций деления.  
  
 Оператор `/=` нельзя перегрузить напрямую, однако пользовательские типы могут перегрузить [оператор /](../../../csharp/language-reference/operators/division-operator.md) (см. [оператор](../../../csharp/language-reference/keywords/operator.md)). В случае всех составных операторов присваивания перегрузка двоичного оператора неявно перегружает эквивалентное составное назначение.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
