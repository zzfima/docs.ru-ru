---
title: "Оператор &amp;&amp; (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 16bc2fa650031d2b1f6cfaf7d128ba487963f707
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
