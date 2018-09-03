---
title: Оператор %= (Справочник по C#)
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: 009c162b13fab05ba349d0535fe8dfae206502f3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399495"
---
# <a name="-operator-c-reference"></a>Оператор %= (Справочник по C#)
Оператор присваивания остатка.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `%=`, такое как  
  
```csharp  
x %= y  
```  
  
 эквивалентно  
  
```csharp  
x = x % y  
```  
  
 за исключением того, что `x` вычисляется только один раз. В числовых типах предварительно определенный [оператор %](../../../csharp/language-reference/operators/remainder-operator.md) используется для вычисления остатка от деления.  
  
 Оператор `%=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор %](../../../csharp/language-reference/operators/remainder-operator.md) (см. [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
