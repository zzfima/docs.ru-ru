---
title: "Оператор || (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '||_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
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
ms.openlocfilehash: 57bcb25b0d453fa59855f40c3189eb4af2bb8b7f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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
  
 [!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

