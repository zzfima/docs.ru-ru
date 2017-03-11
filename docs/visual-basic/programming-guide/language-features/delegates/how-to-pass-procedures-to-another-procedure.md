---
title: "Практическое руководство. Передача процедур другой процедуре в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddressOf - оператор"
  - "делегаты [Visual Basic], процедуры передачи"
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Практическое руководство. Передача процедур другой процедуре в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом примере показано использование делегатов для передачи процедуры другой процедуры.  
  
 Делегат — это тип, который можно использовать как любой другой тип в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Оператор `AddressOf` возвращает объект делегата при применении к имени процедуры.  
  
 В этом примере показана процедура с параметром делегатом, который может принимать ссылку на другую процедуру, полученную с помощью оператора `AddressOf`.  
  
### Создание делегата и согласование процедур  
  
1.  Создайте делегата с именем `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_1.vb)]  
  
2.  Создайте процедуру с именем `AddNumbers` с параметрами и возвращаемым значением, которые совпадают с `MathOperator`, то есть сигнатуры совпадают.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_2.vb)]  
  
3.  Создайте процедуру с именем `SubtractNumbers` с сигнатурой, которая соответствует `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_3.vb)]  
  
4.  Создайте процедуру с именем `DelegateTest`, которая принимает делегат в качестве параметра.  
  
     Эта процедура может принимать ссылку на `AddNumbers` или `SubtractNumbers`, так как их сигнатуре соответствуют сигнатура `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_4.vb)]  
  
5.  Создайте процедуру с именем `Test`, которая сначала вызывает `DelegateTest` с делегатом для `AddNumbers` в качестве параметра и затем снова с делегатом для `SubtractNumbers` в качестве параметра.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-pass-procedures-t_5.vb)]  
  
     Когда вызывается `Test`, то сначала он отображает результат действия `AddNumbers` на значения `5` и `3`, и этот результат равен 8.  Затем отображается результат действия `SubtractNumbers` на `9` и `3`, который равен 6.  
  
## См. также  
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Практическое руководство. Вызов метода делегата](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)