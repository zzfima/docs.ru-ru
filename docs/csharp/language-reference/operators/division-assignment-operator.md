---
title: Оператор /= (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: 8fff048cc441181aa3f0e3c0c638d501aaf9de3f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526312"
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

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
