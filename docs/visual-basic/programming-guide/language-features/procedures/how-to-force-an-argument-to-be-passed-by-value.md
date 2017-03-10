---
title: "Практическое руководство. Принудительная передача аргумента по значению (Visual Basic) | Microsoft Docs"
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
  - "аргументы [Visual Basic], ByVal"
  - "аргументы [Visual Basic], изменение значения"
  - "аргументы [Visual Basic], в круглых скобках"
  - "аргументы [Visual Basic], передача по значению"
  - "аргументы процедур"
  - "аргументы процедур, в круглых скобках"
  - "параметры процедуры"
  - "процедуры, аргументы"
  - "процедуры, вызов"
  - "процедуры, параметры"
  - "код Visual Basic, процедуры"
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Алгоритм передачи определяется в объявлении процедуры.  Если параметр объявляется как [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), то [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ожидает передачи соответствующего аргумента по ссылке.  Это позволяет процедуре изменять значение элемента программирования, содержащегося в аргументе кода вызова.  Если необходимо защитить основные элементы от таких изменений, можно переопределить механизм передачи `ByRef` в процедуре, заключив имя аргумента в скобки.  Эти скобки являются дополнением к круглым скобкам, содержащим список аргументов в вызове.  
  
 Код вызова не может переопределить механизм [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
### Принудительная передача аргумента по значению  
  
-   Если соответствующий параметр объявлен как `ByVal` в процедуре, то необязательно предпринимать дополнительные действия.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] уже ожидает передачи аргумента по значению.  
  
-   Если соответствующий параметр объявлен как `ByRef` в процедуре, заключите аргумент в скобки в вызове процедуры.  
  
## Пример  
 В следующем примере переопределяется объявление параметра `ByRef`.  В вызове, требующем `ByVal`, обратите внимание на два уровня скобок.  
  
 [!code-vb[VbVbcnProcedures#39](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-force-an-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-force-an-argument_2.vb)]  
  
 При `str`, заключенном в дополнительные скобки в списке аргументов, процедуре `setNewString` не удается изменить его значение в коде вызова, и отображается `MsgBox` "Cannot be replaced if passed ByVal".  При `str`, не заключенном в дополнительные скобки, процедура может его изменить и `MsgBox` отображает "This is a new value for the inString argument".  
  
## Компиляция кода  
 Если переменная передается по ссылке, для выбора этого способа необходимо использовать ключевое слово `ByRef`.  
  
 По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для передачи аргументов используется передача по значению.  Однако использование ключевых слов [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) с каждым объявленным параметром — это хороший стиль программирования.  Это облегчает чтение кода.  
  
## Отказоустойчивость  
 Если правильное выполнение кода зависит от изменения базового элемента в вызывающем коде процедуры, объявите параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  Если код вызова переопределяет механизм вызова путем заключения аргумента в круглые скобки, или если он передает немодифицируемый аргумент, в процедуре нельзя изменить основной элемент.  Это может привести к непредсказуемым результатам в коде вызова.  
  
## Безопасность платформы .NET Framework  
 Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде.  Проверьте, что значение будет изменено, и будьте готовы к проверке его допустимости перед использованием.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Различия между аргументами Modifiable и Nonmodifiable](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Различия между передачей аргумента по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Практическое руководство. Изменение значения аргумента процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Практическое руководство. Защита аргумента процедуры от изменения значения](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Передача аргументов по позиции и по имени](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)