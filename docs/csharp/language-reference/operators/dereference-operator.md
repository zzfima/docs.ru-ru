---
title: Оператор -&gt; (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 037229b2081a43077cb4b5d02a8929b06ba9e077
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="-gt-operator-c-reference"></a>Оператор -&gt; (справочник по C#)
Оператор `->` объединяет операции разыменования указателя и доступа к члену.  
  
## <a name="remarks"></a>Примечания  
 Выражение в формате  
  
```csharp  
x->y  
```  
  
 (где `x` — это указатель типа `T*` и `y` — это член `T`) эквивалентно  
  
```csharp  
(*x).y  
```  
  
 Оператор `->` можно использовать только в коде, который помечен как [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
 Оператор `->` перегрузить нельзя.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
