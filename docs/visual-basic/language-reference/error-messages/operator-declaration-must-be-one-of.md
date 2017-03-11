---
title: "В объявлении оператора должен использоваться один из следующих операторов: +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;, =, &lt;&gt;, &lt;, &lt;=, &gt;, &gt;=, CType, IsTrue, IsFalse | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc33000"
  - "vbc33000"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC33000"
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# В объявлении оператора должен использоваться один из следующих операторов: +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;, =, &lt;&gt;, &lt;, &lt;=, &gt;, &gt;=, CType, IsTrue, IsFalse
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Можно объявить только оператор, который подходит для перегрузки.  В следующей таблице перечислены операторы, которые можно объявить.  
  
|Тип|Операторы|  
|---------|---------------|  
|Унарный|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Преобразование \(унарный\)|`CType`|  
  
 Обратите внимание, что оператор `=` в списке бинарных является оператором сравнения, а не оператором присваивания.  
  
 **Идентификатор ошибки**: BC33000  
  
### Чтобы исправить эту ошибку  
  
1.  Выберите оператор из набора перегруженных операторов.  
  
2.  Если требуется функциональная возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте функцию `Function`, которая принимает соответствующие параметры и возвращает соответствующее значение.  
  
## См. также  
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)