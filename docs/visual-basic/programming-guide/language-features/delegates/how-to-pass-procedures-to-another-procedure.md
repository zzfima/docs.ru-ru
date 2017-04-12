---
title: "Практическое руководство: передача процедур другой процедуре в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9865e2d7d3786d289add3fa63b3db777317facdf
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Практическое руководство. Передача процедур другой процедуре в Visual Basic
В этом примере демонстрируется использование делегатов для передачи процедуры другой процедуры.  
  
 Делегат — это тип, который можно использовать как любой другой тип в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. `AddressOf` Оператор возвращает объект делегата при применении к имени процедуры.  
  
 В этом примере показана процедура с параметром делегатом, который может принимать ссылку на другую процедуру, полученную с `AddressOf` оператор.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Создание делегата и согласование процедур  
  
1.  Создать делегат с именем `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, которые совпадают `MathOperator`, то есть подписи совпадают.  
  
     [!code-vb[VbVbalrDelegates&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Создайте процедуру с именем `SubtractNumbers` с сигнатурой, которая соответствует `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates&#3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Создайте процедуру с именем `DelegateTest` , которая принимает делегат в качестве параметра.  
  
     Эта процедура может принимать ссылку на `AddNumbers` или `SubtractNumbers`, так как их сигнатуре соответствуют `MathOperator` подписи.  
  
     [!code-vb[VbVbalrDelegates&#4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Создайте процедуру с именем `Test` , который вызывает `DelegateTest` с делегатом для `AddNumbers` как параметр и снова с делегатом для `SubtractNumbers` как параметр.  
  
     [!code-vb[VbVbalrDelegates&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     При `Test` является именем, то сначала он отображает результат `AddNumbers` на `5` и `3`, который равен 8. Затем результат `SubtractNumbers` на `9` и `3` отображается, который равен 6.  
  
## <a name="see-also"></a>См. также  
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Практическое руководство. Вызов метода делегата](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
