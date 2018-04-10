---
title: Оператор *= (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc2201f78e1e05bd0ccdea04522896c00294bdd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Оператор *= (Справочник по C#)
Бинарный оператор присваивания умножения.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `*=`, такое как  
  
```  
x *= y  
```  
  
 эквивалентно  
  
```  
x = x * y  
```  
  
 за исключением того, что `x` вычисляется только один раз. Для числовых типов [оператор *](../../../csharp/language-reference/operators/multiplication-operator.md) используется для выполнения операций умножения.  
  
 Оператор `*=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор *](../../../csharp/language-reference/operators/multiplication-operator.md) (см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
