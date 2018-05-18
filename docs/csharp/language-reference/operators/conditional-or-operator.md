---
title: Оператор || (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: ce0834874f9c5b4c5154a798492600d6ac45a4c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
