---
title: 'Объявлением оператора должен быть одним из: +,-, *,-, -, ^, &amp;, как и остаток от деления и, Or, Xor, не, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a>Объявлением оператора должен быть один из: +,-, *,\,/, ^, &amp;, такие как остаток от деления и, Or, Xor, не, &lt; &lt;, &gt; &gt;...
Можно объявить только оператор, который подходит для перегрузки. В следующей таблице перечислены операторы, которые могут быть объявлены.  
  
|Тип|Операторы|  
|----------|---------------|  
|Унарный|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Преобразование (унарный)|`CType`|  
  
 Обратите внимание, что `=` в списке бинарных является оператором сравнения, не оператором присваивания.  
  
 **Идентификатор ошибки:** BC33000  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Выберите оператор из набора перегружаемых операторов.  
  
2.  Если требуется возможность перегрузки оператора, который нельзя перегрузить непосредственно, создайте процедуру `Function` , которая принимает соответствующие параметры и возвращает соответствующее значение.  
  
## <a name="see-also"></a>См. также  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Процедуры операторов](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Практическое руководство. Определение оператора](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Практическое руководство. Определение оператора преобразования](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
