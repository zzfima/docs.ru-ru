---
title: Инструкции. Передача процедур в другую процедуру
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 300489935ce54d78b989d09211a7f6ba95c2f514
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345248"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Практическое руководство. Передача процедур другой процедуре в Visual Basic
В этом примере показано, как использовать делегаты для передачи процедуры в другую процедуру.  
  
 Делегат — это тип, который можно использовать как любой другой тип в Visual Basic. Оператор `AddressOf` возвращает объект делегата при применении к имени процедуры.  
  
 Этот пример содержит процедуру с параметром делегата, который может принимать ссылку на другую процедуру, полученную с помощью оператора `AddressOf`.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Создание делегата и процедур сопоставления  
  
1. Создайте делегат с именем `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, которые соответствуют значениям `MathOperator`, чтобы сигнатуры совпадали.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Создайте процедуру с именем `SubtractNumbers` с сигнатурой, которая соответствует `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Создайте процедуру с именем `DelegateTest`, которая принимает делегат в качестве параметра.  
  
     Эта процедура может принять ссылку на `AddNumbers` или `SubtractNumbers`, так как их сигнатуры соответствуют подписи `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Создайте процедуру с именем `Test`, которая вызывает `DelegateTest` один раз с делегатом для `AddNumbers` в качестве параметра и снова с делегатом для `SubtractNumbers` в качестве параметра.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     При вызове `Test` сначала отображается результат `AddNumbers`, действующего на `5` и `3`, что равно 8. Затем отображается результат `SubtractNumbers`, действующего в `9` и `3`, что равно 6.  
  
## <a name="see-also"></a>См. также

- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Практическое руководство. Вызов метода делегата](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
