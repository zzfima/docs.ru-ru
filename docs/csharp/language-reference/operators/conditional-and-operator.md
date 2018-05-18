---
title: Оператор &amp;&amp; (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 86508c6eeb2998c6f202608f9204b72b60786e4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ampamp-operator-c-reference"></a>Оператор &amp;&amp; (справочник по C#)
Условный оператор И (`&&`) выполняет логическую операцию И применительно к своим операндам типа `bool`, но вычисляет только второй операнд при необходимости.  
  
## <a name="remarks"></a>Примечания  
 Операция  
  
```  
x && y  
```  
  
 соответствует операции  
  
```  
x & y  
```  
  
 за исключением того, что если `x` имеет значение `false`, `y` не вычисляется, так как результат операции И — `false` независимо от того, какое значение имеет `y`. Это называется сокращенным вычислением.  
  
 Оператор условного И не может быть перегружен, но перегрузки регулярных логических операторов и операторов [true](../../../csharp/language-reference/keywords/true.md) и [false](../../../csharp/language-reference/keywords/false.md) могут, с некоторыми ограничениями, считаться перегрузками условных логических операторов.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере условное выражение во втором операторе `if` вычисляет только первый операнд, так как операнд возвращает `false`.  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
