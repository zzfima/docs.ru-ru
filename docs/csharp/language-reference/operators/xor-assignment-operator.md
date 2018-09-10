---
title: Оператор ^= (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: d6546f23ffb6dee792339a7e3863bf58ae668d58
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857236"
---
# <a name="-operator-c-reference"></a>Оператор ^= (справочник по C#)
Оператор присваивания исключающего ИЛИ.  
  
## <a name="remarks"></a>Примечания  
 Выражение в формате  
  
```csharp  
x ^= y  
```  
  
 вычисляется как  
  
```csharp  
x = x ^ y  
```  
  
 за исключением того, что `x` вычисляется только один раз. [Оператор ^](../../../csharp/language-reference/operators/xor-operator.md) выполняет побитовую операцию исключающего ИЛИ в отношении целочисленных операндов и логическую операцию исключающего ИЛИ в отношении операндов типа [bool](../../../csharp/language-reference/keywords/bool.md).  
  
 Оператор ^= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор ^](../../../csharp/language-reference/operators/xor-operator.md) (см. [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
