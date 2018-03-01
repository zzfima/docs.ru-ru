---
title: "Оператор || (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b95fd162c9a89789e1970b32473c8acf16ba5cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Оператор || (Справочник по C#)
Оператор условного ИЛИ (`||`) выполняет логическую операцию ИЛИ со всеми своими операндами типа `bool`. Если результатом первого операнда является значение `true`, второй операнд не вычисляется. Если первый операнд имеет значение `false`, второй оператор будет определять итоговое значение выражения ИЛИ (`true` или `false`).  
  
## <a name="remarks"></a>Примечания  
 Операция  
  
```  
x || y  
```  
  
 соответствует операции  
  
```  
x | y  
```  
  
 кроме случаев, когда `x` имеет значение `true`. В таких ситуациях `y` не вычисляется, поскольку операция ИЛИ будет возвращать значение `true` независимо от значения `y`. Это называется сокращенным вычислением.  
  
 Оператор условного ИЛИ не может быть перегружен, но перегрузки регулярных логических операторов и операторов [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md) могут, с некоторыми ограничениями, считаться перегрузками условных логических операторов.  
  
## <a name="example"></a>Пример  
 В следующих примерах в выражении, использующем оператор `||`, вычисляется только первый операнд. В выражении с оператором `|` вычисляются оба операнда. Во втором примере в случае вычисления обоих операндов возникает исключение времени выполнения.  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
