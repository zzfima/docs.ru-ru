---
title: "Практическое руководство. Изменение значения аргумента процедуры (Visual Basic) | Microsoft Docs"
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
  - "аргументы [Visual Basic], ByRef"
  - "аргументы [Visual Basic], ByVal"
  - "аргументы [Visual Basic], изменение значения"
  - "аргументы [Visual Basic], передача по ссылке"
  - "аргументы [Visual Basic], передача по значению"
  - "аргументы процедур"
  - "параметры процедуры"
  - "процедуры, аргументы"
  - "процедуры, параметры"
  - "код Visual Basic, процедуры"
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

При вызове процедуры каждый аргумент соответствует одному из параметров, определенных в процедуре.  В некоторых случаях код процедуры может изменять значение основного аргумента в вызывающем коде.  В других случаях процедура может изменять только его локальную копию.  
  
 При вызове процедуры [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] создает локальную копию каждого аргумента, который передается [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  Для каждого передаваемого аргумента [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет для кода процедуры прямую ссылку на элемент программирования, содержащегося в аргументе в вызывающем коде.  
  
 Если базовый элемент вызывающего кода является изменяемым, и аргумент передается `ByRef`, то код процедуры позволяет изменить значение элемента в коде вызова при помощи прямой ссылки.  
  
## Изменение базового значения  
  
#### Для изменения базового значения аргумента процедуры в коде вызова  
  
1.  В объявлении процедуры укажите [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для параметра, соответствующего аргументу.  
  
2.  В вызывающем коде передайте изменяемый элемент программирования в качестве аргумента.  
  
3.  В вызывающем коде не заключайте аргумент в список аргументов в скобках.  
  
4.  В коде процедуры используйте имя параметра для присвоения значения базовому элементу в вызывающем коде.  
  
 Посмотрите следующий пример.  
  
## Изменение локальных копий  
 Если базовый элемент в вызывающем коде является неизменяемым или аргумент передается `ByVal`, то процедура не может изменять его значение в вызывающем коде.  Однако процедура может изменить локальную копию такого аргумента.  
  
#### Чтобы изменить копию аргумента процедуры в коде процедуры  
  
1.  В объявлении процедуры укажите [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для параметра, соответствующего аргументу.  
  
     \-или\-  
  
     В вызывающем коде заключите аргумент в список аргументов в скобках.  Это указывает [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] передавать аргумент по значению, даже если соответствующий параметр указывает `ByRef`.  
  
2.  В коде процедуры используйте имя параметра для присвоения значения локальной копии аргумента.  Основное значение в коде вызова не изменяется.  
  
## Пример  
 В следующем примере показаны две процедуры, которые принимают переменную массива и производят действия над его элементами.  Процедура `increase` добавляет единицу к каждому элементу.  Процедура `replace` присваивает новый массив параметру `a()` и добавляет единицу к каждому элементу.  
  
 [!code-vb[VbVbcnProcedures#35](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-change-the-value-_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-change-the-value-_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-change-the-value-_3.vb)]  
  
 Первый вызов `MsgBox` выводит следующее: "After increase\(n\): 11, 21, 31, 41".  Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на механизм передачи `ByVal`.  
  
 Второй вызов `MsgBox` выводит следующее: "After replace\(n\): 101, 201, 301".  Так как объект `n` передается механизмом `ByRef`, `replace` может изменить переменную `n` в вызывающем коде и присвоить ей новый массив.  Поскольку  `n`  является ссылочным типом,  `replace`  может изменять его члены.  
  
 Можно запретить процедуре изменять переменную в вызывающем коде.  См. раздел [Практическое руководство. Защита аргумента процедуры от изменения значения](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## Компиляция кода  
 Если переменная передается по ссылке, для выбора этого способа необходимо использовать ключевое слово `ByRef`.  
  
 По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для передачи аргументов используется передача по значению.  Однако использование ключевых слов [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) с каждым объявленным параметром — это хороший стиль программирования.  Это облегчает чтение кода.  
  
## Безопасность платформы .NET Framework  
 Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде.  Проверьте, что значение будет изменено, и будьте готовы к проверке его допустимости перед использованием.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Различия между аргументами Modifiable и Nonmodifiable](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Различия между передачей аргумента по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Практическое руководство. Защита аргумента процедуры от изменения значения](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Практическое руководство. Принудительная передача аргумента по значению](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Передача аргументов по позиции и по имени](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)