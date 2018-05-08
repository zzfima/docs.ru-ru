---
title: 'Объявлением оператора должен быть одним из: +,-, *,-, -, ^, &amp;, как и остаток от деления и, Or, Xor, не, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; , &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: eb1e7e8088ec8661be2469aff043c0f1a96e4d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
