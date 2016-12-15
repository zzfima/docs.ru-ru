---
title: "Практическое руководство. Защита аргумента процедуры от изменения значения (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "аргументы [Visual Basic], ByRef"
  - "аргументы [Visual Basic], ByVal"
  - "аргументы [Visual Basic], изменение значения"
  - "аргументы [Visual Basic], передача по ссылке"
  - "аргументы [Visual Basic], передача по значению"
  - "аргументы процедур"
  - "параметры процедуры"
  - "процедуры, аргументы"
  - "процедуры, вызов"
  - "процедуры, параметры"
  - "код Visual Basic, процедуры"
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Защита аргумента процедуры от изменения значения (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Если процедура объявляет параметр как [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), то [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] передает в код процедуры прямую ссылку на программный элемент, лежащий в основе аргумента в вызывающем коде.  Это позволяет процедуре изменять значение, содержащееся в аргументе в вызывающем коде.  В некоторых случаях вызывающему коду может потребоваться защита от таких изменений.  
  
 Всегда можно защитить аргумент от изменений, объявив соответствующий параметр [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) в процедуре.  Если в некоторых случаях требуется изменять данный аргумент, но не другие, то можно объявить его `ByRef` и позволить вызывающему коду определять механизм передачи в каждом вызове.  Это делается путем заключения в скобки соответствующего аргумента для передачи его по значению или без круглых скобок для передачи его по ссылке.  Дополнительные сведения см. в разделе [Практическое руководство. Принудительная передача аргумента по значению](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md).  
  
## Пример  
 В следующем примере показаны две процедуры, которые принимают переменную массива и производят действия над его элементами.  Процедура `increase` добавляет единицу к каждому элементу.  Процедура `replace` присваивает новый массив параметру `a()` и добавляет единицу к каждому элементу.  Однако это переопределение не влияет на базовую переменную массива в вызывающем коде.  
  
 [!code-vb[VbVbcnProcedures#35](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 Первый вызов `MsgBox` выводит следующее: "After increase\(n\): 11, 21, 31, 41".  Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на механизм передачи `ByVal`.  
  
 Второй вызов `MsgBox` выводит следующее: "After replace\(n\): 11, 21, 31, 41".  Так как объект `n` передается механизмом `ByVal`, `replace` не может изменить переменную `n` в вызывающем коде, присвоив ей новый массив.  Когда `replace` создает новый экземпляр массива `k` и присваивает его к локальной переменной `a`, он теряет ссылку на `n` , переданную вызывающим кодом.  Когда он изменяет элементы `a`, изменяется только локальный массив `k` .  Таким образом, `replace` не увеличивает значения из массива `n` в вызывающем коде.  
  
## Компиляция кода  
 По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для передачи аргументов используется передача по значению.  Однако использование ключевых слов [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) с каждым объявленным параметром — это хороший стиль программирования.  Это облегчает чтение кода.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Различия между аргументами Modifiable и Nonmodifiable](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Различия между передачей аргумента по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Практическое руководство. Изменение значения аргумента процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Практическое руководство. Принудительная передача аргумента по значению](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Передача аргументов по позиции и по имени](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)