---
title: "Практическое руководство. Вызов перегруженной процедуры (Visual Basic) | Microsoft Docs"
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
  - "вызовы процедур, перегруженные"
  - "процедуры, вызов"
  - "процедуры, несколько версий"
  - "процедуры, перегрузка"
  - "код Visual Basic, процедуры"
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Практическое руководство. Вызов перегруженной процедуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Преимущество перегрузки процедуры заключается в гибкости вызова.  Код вызова может получать информацию, которую ему необходимо передать в процедуру, а затем вызвать одну процедуры по имени, независимо от того, какие аргументы она передает.  
  
### Вызов процедуры, для которой определено более одной версии  
  
1.  В коде вызова определите, какие данные необходимо передать в процедуру.  
  
2.  Напишите вызов процедуры обычным способом, представляя данные в списке аргументов.  Убедитесь, что аргументы соответствуют списку параметров в одной из определенных версий процедуры.  
  
3.  Нет необходимости определять, какую версию процедуры следует вызвать.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] передает управление той версии, которая соответствует списку аргументов.  
  
     В следующем примере вызывается процедура `post`, объявленная в [Практическое руководство. Определение различных версий процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md).  Она получает идентификатор клиента, определяет, является он `String` или `Integer`, а затем в любом случае вызывает ту же процедуру.  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Устранение неполадок в процедурах](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Практическое руководство. Определение различных версий процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Вопросы, связанные с перегрузкой процедур](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Разрешение перегрузки](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)