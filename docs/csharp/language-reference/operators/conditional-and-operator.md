---
title: "Оператор &amp;&amp; (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1da61947cbc85e5b3045513e99e013d1e4fae4b3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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
  
 [!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

