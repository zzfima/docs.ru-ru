---
title: "Передача аргументов по позиции и по имени (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - ":= - передача аргументов"
  - "передача аргументов"
  - "передача аргументов, по позиции"
  - "аргументы [Visual Basic], перечисление по имени"
  - "аргументы [Visual Basic], передача по имени"
  - "аргументы [Visual Basic], передача по позиции"
  - "процедуры функций, передача аргументов"
  - "именованные аргументы"
  - "именованные аргументы, передача аргументов"
  - "именованные параметры"
  - "именованные параметры, передача аргументов"
  - "передача параметров, по имени"
  - "передача параметров, по позиции"
  - "передача параметров, именованные аргументы параметров"
  - "аргументы процедур"
  - "процедуры, аргументы"
  - "процедуры, вызов"
  - "Sub - процедуры, передача аргументов"
  - "код Visual Basic, процедуры"
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Передача аргументов по позиции и по имени (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

При вызове процедуры `Sub` или `Function`, можно передать аргументы *по позиции* в порядке, в котором они отображаются в определении процедуры, и *по имени*, без учета этого порядка.  
  
 Когда аргумент передается по имени, необходимо указать его объявленное имя, затем двоеточие со знаком равенства \(`:=`\) и значение аргумента.  Именованные аргументы можно указывать в любом порядке.  
  
 Например, приведенная ниже процедура `Sub` принимает три аргумента:  
  
 [!code-vb[VbVbcnProcedures#41](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 При вызове этой процедуры аргументы можно задавать по позиции, по имени или обоими способами.  
  
## Передача аргументов по позиции  
 Процедуру `studentInfo` можно вызвать с передачей аргументов по позиции, разделяя их запятыми, как показано в следующем примере:  
  
 [!code-vb[VbVbcnProcedures#42](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 Если какой\-либо необязательный аргумент в позиционном списке будет опущен, необходимо отметить его место запятой.  В следующем примере вызывается `studentInfo` без аргумента `age` :  
  
 [!code-vb[VbVbcnProcedures#43](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## Передача аргументов по имени  
 С другой стороны, можно вызвать процедуру `studentInfo` с аргументами, переданными по имени и также разделенными запятыми, как показано в следующем примере:  
  
 [!code-vb[VbVbcnProcedures#44](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## Смешанная передача аргументов по позиции и по имени  
 В одном вызове процедуры можно передавать аргументы и по позиции, и по имени, как показано в следующем примере:  
  
 [!code-vb[VbVbcnProcedures#45](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 В этом примере дополнительная запятая, отмечающая пропущенный аргумент `age` , не требуется, поскольку аргумент `birth` передается по имени.  
  
 Если аргументы передаются и по позиции, и по имени, то сначала следует указывать все позиционные аргументы.  После первого аргумента, передаваемого по имени, все последующие аргументы также должны быть заданы по имени.  
  
## Задание необязательных аргументов по имени  
 Передача аргументов по имени особенно удобна при вызове процедуры с несколькими необязательными аргументами.  Если аргументы задаются по имени, это позволяет опускать позиционные аргументы, не отмечая их подряд идущими запятыми.  Кроме того, при передаче аргументов по имени легче следить за тем, какие аргументы заданы, а какие пропущены.  
  
## Ограничения при передаче аргументов по имени  
 Аргументы нельзя передавать по имени, чтобы избежать ввода обязательных аргументов.  Опускать можно только необязательные аргументы.  
  
 Не допускается передача массива параметров по имени.  Это объясняется тем, что число аргументов для массива, задаваемых через запятую при вызове процедуры, не определено, а компилятор не может связать с одним именем более одного аргумента.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Практическое руководство. Передача аргументов в процедуру](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Необязательные параметры](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Массивы параметров](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)   
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)