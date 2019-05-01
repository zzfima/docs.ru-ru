---
title: Практическое руководство. Передача процедур другой процедуре в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 312c0e0f100e85256ad4ca856ccf7f35dbaa36dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973294"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Практическое руководство. Передача процедур другой процедуре в Visual Basic
В этом примере показано, как использование делегатов для передачи процедур другой процедуре.  
  
 Делегат — это тип, который можно использовать как любой другой тип в Visual Basic. `AddressOf` Оператор возвращает объект делегата при применении к имени процедуры.  
  
 В этом примере показана процедура с параметром делегатом, который может принимать ссылку на другую процедуру, полученную с `AddressOf` оператор.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Создание делегата и согласование процедур  
  
1. Создать делегат с именем `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, которые совпадают `MathOperator`, так что подписи совпадают.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Создайте процедуру с именем `SubtractNumbers` с сигнатурой, которая соответствует `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Создайте процедуру с именем `DelegateTest` , принимает делегат в качестве параметра.  
  
     Эта процедура может принимать ссылку `AddNumbers` или `SubtractNumbers`, так как их сигнатуры совпадают `MathOperator` подписи.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Создайте процедуру с именем `Test` , который вызывает `DelegateTest` с делегатом для `AddNumbers` как параметр и снова с делегатом для `SubtractNumbers` как параметр.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     При `Test` является именем, то сначала он отображает результат `AddNumbers` на `5` и `3`, который равен 8. Затем результат `SubtractNumbers` на `9` и `3` отображается, который равен 6.  
  
## <a name="see-also"></a>См. также

- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Практическое руководство. Вызов метода делегата](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
